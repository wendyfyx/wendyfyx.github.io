---
layout: page
permalink: /projects/index.html
title: Projects
---

<style>
    /* Project cards */
.project-card {
  background-color: aliceblue;
  border-radius: 10px;
  float: left;
  /* width: calc(50% - 20px); */
  width: 75%;
  padding: 10px;
  margin: 10px;
  /* height: 145px; */
  box-shadow: 0 2px 3px 0 rgba(0, 0, 0, 0.05);
  transition: 0.3s;
}

.project-card:hover {
  cursor: pointer;
  transform: translate(0, -3px);
}

.project-card-container:after {
  content: "";
  display: table;
  clear: both;
}

.project-title {
  display: grid;
  align-items: end;
  gap: 0 .25rem;
  grid-template-columns: auto max-content;
  grid-template-areas: "chapter page";

  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
  /* color: #268bd2; */
  margin-top: 5px;
  margin-bottom: 0;
  font-weight: bold;
  font-size: 1.17em;
  /* justify-content: space-between; */
}

.chapter {
  grid-area: chapter;
  position: relative;
  overflow: hidden;
}
.chapter::after {
  position: absolute;
  padding-left: .25ch;
  content: " . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . "
  ". . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . "
  ". . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . ";
  text-align: right;
}
.page {
  grid-area: page;
}

.project-tagline {
  color: rgb(140, 140, 140);
  font-style: italic;
  margin-bottom: 3px;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;

}

.project-description {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}

</style>

<div class="project-card-container">
    {% for project in site.projects reversed %}
    <div class="project-card" onclick="location.href='{{ project.url }}';">
        <div class="project-header">
            <div class="project-title">
                <div class="chapter"><a href="{{ project.url }}">{{ project.title }}</a></div>
                <div class="dots"></div>
                <div class="page">{{ project.date | date: "%Y" }}</div>
            </div>
            <div class="project-tagline">{{ project.tagline }}</div>
        </div>
        <div class="project-description">
            {{ project.description }}
        </div>
    </div>
    {% endfor %}
</div>
