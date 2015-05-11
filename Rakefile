
task :meetup do
  info = get_info(yyyy: 'Year (YYYY)', mm: 'Month (mm)', dd: 'Day (dd)', venue: 'Venue')

  date = Time.new(info[:yyyy], info[:mm], info[:dd], 14, 0, 0)
  month_name = date.strftime('%B').downcase

  text = "---
layout: post
title: \"Kochi Ruby Meetup - #{date.strftime('%d %B, %Y')}\"
date:  #{date.strftime('%Y-%m-%d %k:%M:%S')}
categories: meetups
---
  
**RSVP**:

# Agenda

* 2:00 - Introductions
* 2:30 - Talks...

**Date**: 2-5pm, #{date.strftime('%d %B, %Y')}

**Venue**: #{info[:venue]}
"

  filename = "#{date.strftime '%Y-%m-%d'}-kochi-meetup-#{month_name}-#{info[:yyyy]}.md"
  path = File.join('_posts', filename)
  File.open(path, 'w') { |f| f << text }
end

def get_info(qns)
  qns.map { |k, qn|
    [k, ask("#{qn}: ")]
  }.to_h
end

def ask(qn)
  STDOUT.print qn
  STDIN.gets.chomp
end

