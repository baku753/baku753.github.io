# タッタの日記

{% assign dummy_for_break = "" %}

{%- for post in site.posts -%}
  {%- if post.title contains ".en" -%}
  {%- else -%}
    {%- assign temp_month = post.date | date: "%Y.%-m" -%}
    {%- if temp_month != currentmonth -%}
      {%- if currentmonth -%}</div>{%- endif -%}
      {%- assign currentmonth = temp_month -%}
      <h2 class="month">{{- currentmonth -}}</h2><div class="posts">
    {%- else -%}
      &nbsp;<span class="understatement">/</span>&nbsp;
    {%- endif -%}
    {%- assign temp_h1 = post.excerpt | split: "</h1>" | first | strip_html -%}
    <a href="{{-post.url-}}">{{- temp_h1 -}}</a>
  {%- endif -%}
{%- endfor -%}</div>
