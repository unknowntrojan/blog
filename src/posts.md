---
layout: page
title: Posts
---

<div class="flex m-auto flex-col" markdown="0">
{% for post in collections.posts.resources %}
    <div class="grow p-4 bg-zinc-800 mb-4">
		<div class="grid grid-flow-row grid-cols-2">
			<div class="mb-0">
				<a href="{{ post.relative_url }}">
					<h1 class="text-gray-100 mb-2">{{ post.data.title }}</h1>
				</a>
				<div class="grid grid-flow grid-rows-3 mb-0">
					<p class="mb-0">
						<i class="fa-regular fa-calendar mr-1"></i>
						{{ post.date | date: "%-d %B %Y" }}
					</p>
					<p class="mb-0">
						<i class="fa-regular fa-hashtag mr-1"></i>
						{{ post.content | strip_html | number_of_words }} words
					</p>
					<p class="mb-0">
						<i class="fa-regular fa-clock mr-1"></i>
						{{ post.content | reading_time }}
					</p>
				</div>				
			</div>
			<div>
				<p class="text-gray-400 text-sm mb-0 line-clamp-4">
					{{ post.summarytext | strip_html }}
				</p>
			</div>
		</div>
    </div>
{% else %}
<h2 class="text-center">Nothing yet :/</h2>
{% endfor %}
</div>