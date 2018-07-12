require 'rake'
require 'yaml'

SOURCE = "."
CONFIG = {
  'posts' => File.join(SOURCE, "_posts"),
  'post_ext' => "md",
}

# Usage: rake post title="A Title"
desc "Begin a new post in #{CONFIG['posts']}"

task :post do
  abort("rake aborted: '#{CONFIG['posts']}' directory not found.") unless FileTest.directory?(CONFIG['posts'])
  
  
  if !ENV["title"]
    puts "标题："
    title = STDIN.gets.chomp
  else
    title = ENV["title"]
  end



  while title == '' || title.downcase.strip.gsub(' ', '').length == 0
    puts "标题："
    title = STDIN.gets.chomp
  end

  @slug = title.downcase.strip.gsub(' ', '-').gsub(/[^\w-]/, '')

  puts "文章categories，以空格分隔："
  @categories = STDIN.gets.chomp

  puts "文章tag："
  @tag = STDIN.gets.chomp


  # 创建文件 
  @filename = File.join(CONFIG['posts'], "#{Time.now.strftime('%Y-%m-%d')}-#{@slug}.#{CONFIG['post_ext']}")
  if File.exist?(@filename)
    abort("rake aborted!") if ask("#{@filename} already exists. Do you want to overwrite?", ['y', 'n']) == 'n'
  end

  # 写入相关属性
  puts "Creating new post: #{@filename}"
  open(@filename, 'w') do |post|
    post.puts "---"
    post.puts "layout: post"
    post.puts "title: \"#{title.gsub(/-/,' ')}\""
    post.puts "excerpt: \"\""
    post.puts "category: #{@categories}"
    post.puts "tags: #{@tag}"
    post.puts "---"
  end
end # task :post







task :sp do
  abort("rake aborted: '#{CONFIG['posts']}' directory not found.") unless FileTest.directory?(CONFIG['posts'])
  
  if !ENV["title"]
    puts "标题："
    title = STDIN.gets.chomp
  else
    title = ENV["title"]
  end

  while title == '' || title.downcase.strip.gsub(' ', '').length == 0
    puts "标题："
    title = STDIN.gets.chomp
  end

  @slug = title.downcase.strip.gsub(' ', '-').gsub(/[^\w-]/, '')

  # 创建文件 
  @filename = File.join(CONFIG['posts'], "#{Time.now.strftime('%Y-%m-%d')}-#{@slug}.#{CONFIG['post_ext']}")
  if File.exist?(@filename)
    abort("rake aborted!") if ask("#{@filename} already exists. Do you want to overwrite?", ['y', 'n']) == 'n'
  end

  # 写入相关属性
  puts "Creating new post: #{@filename}"
  open(@filename, 'w') do |post|
    post.puts "---"
    post.puts "layout: post"
    post.puts "title: \"#{title.gsub(/-/,' ')}\""
    post.puts "category: "
    post.puts "excerpt: \"\""
    post.puts "tags: []"
    post.puts "---"
  end
end