---
title: "Présentation"
layout: page-sidebar
permalink: "/about.html"
image: "/assets/images/lab.jpg"
comments: false
---

<h3 class="border-bottom mb-4">Le projet</h3>

La Plateforme Expérimentale en Robotique Mobile Intelligente et Systems est dédiée à
l’apprentissage via des projets recherche en navigation autonome dans des conditions dégradées et en aide à la personne (HMI)

La plateforme est un local d’environ 40m2, composée d’une grande salle avec un grand écran pour les démos, un
bureau pour les ingénieurs ( capacité : 3 ingénieurs) et une salle de 8m2 dédiée à la simulation des conditions
dégradées (brouillard, pluie).

N'hésitez pas à supporter le projet <i class="fa fa-heart text-danger"></i>.
<br>
<h3 class="border-bottom mb-4">Le matériel</h3>


<div class="card mx-auto mb-1 border-0"  style="max-width: 100%;">
  <div class="card-header">
    <ul class="nav nav-tabs card-header-tabs" id="test-list" role="tablist">
      {% for section in site.data.material_sections %}
        {% if section.first %}
          <li class="nav-item">
            <a class="nav-link shadow-none active" id="{{ section.jsid }}" href="#{{section.id}}" role="tab" aria-controls="{{section.id}}" aria-selected="true">{{section.name}}</a>
          </li>
        {% else %}
          <li class="nav-item">
              <a class="nav-link" id="{{ section.jsid }}" href="#{{section.id}}" role="tab" aria-controls="{{section.id}}" aria-selected="true">{{section.name}}</a>
          </li>
        {% endif %}
      {% endfor %}
    </ul>
  </div>
  <div class="card-body">          
      <div class="tab-content">
        {% for section in site.data.material_sections %}
          {% if section.first %}
            {% if section.name == "Robots" %}
              <div class="tab-pane active overflow-auto" id="{{section.id}}" role="tabpanel">
	            {% for robot in site.data.robots %}
	              <div class="card mb-3">
				  	<div class="card-body">
				    	<h5 class="card-title">{{ robot.name }}</h5>
				    	<p class="card-text">{{ robot.description }}</p>
				    	<a href="{{ robot.link }}" class="btn btn-primary">Découvrir &rarr;</a>
				  	</div>
				  </div>
	            {% endfor %}
	          </div>
            {% else %}
              <div class="tab-pane overflow-auto" id="{{section.id}}" role="tabpanel">
                <p class="card-text">{{section.description}}</p>
              </div>
            {% endif %}
          {% else %}  
            {% if section.name == "Capteurs" %}
              <div class="tab-pane overflow-auto" id="{{section.id}}" role="tabpanel" aria-labelledby="{{section.id}}-tab">  
	            {% for capteur in site.data.capteurs %}
	              <div class="card mb-3">
				  	<div class="card-body">
				    	<h5 class="card-title">{{ capteur.name }}</h5>
				    	<p class="card-text">{{ capteur.description }}</p>
				    	<a href="{{ capteur.link }}" class="btn btn-primary">Découvrir &rarr;</a>
				  	</div>
				  </div>
	             {% endfor %}         
	          </div>
            {% elsif section.name == "Systèmes" %}
              <div class="tab-pane overflow-auto" id="{{section.id}}" role="tabpanel" aria-labelledby="{{section.id}}-tab">  
                    {% for system in site.data.systems %}
                      <div class="card mb-3">
				  	    <div class="card-body">
				    	  <h5 class="card-title">{{ system.name }}</h5>
				    	  <p class="card-text">{{ system.description }}</p>
				    	  <a href="{{ system.link }}" class="btn btn-primary">Découvrir &rarr;</a>
				  	    </div>
				      </div>
                    {% endfor %}
              </div>
            {% else %}
              <div class="tab-pane overflow-auto" id="{{section.id}}" role="tabpanel" aria-labelledby="{{section.id}}-tab">  
                <h5 class="card-title text-center"><a href="/{{ section.url }}" class="highlighted">{{section.description}}</a></h5>
                <p class="card-text">{{ section.content }} </p>              
              </div>
            {% endif %}
          {% endif %}
        {% endfor %}
      </div>
</div>



<script>
    $('#test-list a').on('click', function (e) {
    	e.preventDefault()
    	$(this).tab('show')
    })
</script> 
