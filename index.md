Hi, I'm shine.

<div>
	{% for post in site.posts %}
		<h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
			{{ post.excerpt }}
	{% endfor %}
</div>
