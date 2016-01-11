require 'aws-sdk'
require 'yaml'
require 'ruby-progressbar'
require 'mimetype_fu'
require 'dotenv'
Dotenv.load

# Amazon S3 code based on code from http://bit.ly/1kXJRJF
Aws.config.update({
  region: ENV['REGION'],
  credentials: Aws::Credentials.new(ENV['ACCESS_KEY'], ENV['SECRET_KEY'])
})
@aws_bucket = ENV['S3_BUCKET']
@assets = '_assets'

desc "Upload all assets to Amazon S3"
task :upload_assets => [:upload_images] do
  puts "All Assets uploaded!"
end

desc "Upload images assets to Amazon S3"
task :upload_images do
  raise "assets directory doesn't exist" unless File.directory?(@assets)
  Dir.chdir(@assets)

  if File.directory?("images") then
    assets = Dir.glob("images/**/*.*")

    @progress = ProgressBar.create()
    @progress.total = assets.count
    @progress.format = "[Images] Processing: %c from %C | %t"

    for asset in assets
      upload(asset)
      @progress.increment
    end
  end

  Dir.chdir(File.dirname(__FILE__))
end

def upload(asset)
  begin
    options = {
      acl: "public-read",
      cache_control: "public; max-age=86400",
      content_type: File.mime_type?(asset)
    }

    s3 = Aws::S3::Resource.new
    bucket = s3.bucket(@aws_bucket)

    if !bucket.exists? then
      #abort("rake aborted!") if ask("#The bucket {@aws_bucket} doesn't exists. Do you want to create it?", ['y', 'n']) == 'n'
      puts "The bucket #{@aws_bucket} doesn't exists, creating bucket #{@aws_bucket}"
      bucket = s3.create_bucket(bucket: @aws_bucket)
    end

    force_update = !!ENV["FORCE_UPDATE"] || false

    force = "[OVERWRITTING]" if force_update
    object = bucket.object(asset)

    object_exist = object.exists?
    asset_changed = File.size(asset) != object.size if object_exist

    if !object_exist || force_update || asset_changed then
      @progress.title = "Uploading #{File.basename(asset)} #{force}"
      bucket.object(asset).upload_file(asset, options)
    else
      @progress.title = "Skipping #{File.basename(asset)} [UP TO DATE]"
    end
  rescue Aws::S3::MultipartUploadError => e
    puts e.errors
  end
end
