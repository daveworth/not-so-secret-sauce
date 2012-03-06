desc "Generate new topic"
task :new do
  title = ENV["title"] || "New Title"
  slug = title.gsub(' ','-').downcase

  filename = "#{slug}.md"

  path = File.join('topics', filename)
  post = <<-HEAD
---
layout: topic
title: #{title}
published: false
image_hint_url: http://full/path/to/image/for/hinting/social/media/scrapers.png
description: Description for social media
---

Body of content goes here!

HEAD

  File.open(path, 'w') do |file|
    file.puts post
  end
  puts "New topic skeleton generated in #{path}"
end
