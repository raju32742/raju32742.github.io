
<style>
.badge {
  display: inline-block;
  padding: 0.10em 0.55em;     /* less vertical/horizontal padding */
  margin: 0 3px 6px 0;        /* tighter, less gap between */
  font-size: 13px;            /* smaller for tag feel */
  color: #fff;
  background-color: #2637a1;  /* your blue */
  border-radius: 16px;        /* slightly rounder */
  font-weight: 500;           /* medium, not bold */
  letter-spacing: 0.02em;
  line-height: 1.5;
  box-shadow: 0 1px 2px rgba(0,0,0,0.05);
  vertical-align: middle;
  transition: background 0.2s;
}

.badge:hover {
  background-color: #1a237e;
  cursor: pointer;
}

.work-details ul {
    margin-bottom: 0.2em !important;
}
.work-details ul ul {
    margin-bottom: 0 !important;   /* For nested lists */
    margin-top: 0 !important;
}

</style>


<h1 id="work-experience"></h1>

<h2 style="margin: 60px 0px 15px;">Work Experience</h2>
<div style="height:15px;"></div>



<div class="work-experience">
  <ul class="work-exp-list" style="list-style: none; padding-left: 0;">
    {% for job in site.data.work_experience.work_experience %}
    <li class="work-exp-item" style="margin-bottom: 40px;">
      <div class="work-header" style="display: flex; align-items: center; gap: 16px;">
        {% if job.logo %}
          <img src="{{ job.logo }}" alt="{{ job.company }} logo" class="work-logo"
            style="height: 54px; width: 54px; object-fit: contain; margin: 0; display: block;">
        {% endif %}
        <div>
          <h3 style="margin:0 0 2px 0; font-size:1.18em; font-weight: 600; line-height: 1.2;">
            {{ job.position }}
          </h3>
          <span class="work-company" style="font-weight:500;">
            {{ job.company }}
          </span>
          | <span class="work-location" style="color:#444;">
            {{ job.location }}
          </span>
          | <span class="work-dates" style="color:#666; font-size: 0.97em;">
            {{ job.start_date }} – {{ job.end_date }}
          </span>
        </div>
      </div>
      <ul class="work-details" style="margin: 10px 0 6px 0; padding-left: 26px;">
        {% for item in job.description %}
          {% if item contains 'courses' %}
            <li>
              Taught undergraduate courses:
              <ul style="padding-left:20px;">
                {% for course in item.courses %}
                  <li>{{ course }}</li>
                {% endfor %}
              </ul>
            </li>
          {% else %}
            <li>{{ item }}</li>
          {% endif %}
        {% endfor %}
      </ul>
      {% if job.skills %}
      <div class="work-skills" style="margin-top: 7px;padding-left: 20px;">
        {% for skill in job.skills %}
        <span class="badge">{{ skill }}</span>
        {% endfor %}
      </div>
      {% endif %}
    </li>
    {% endfor %}
  </ul>
</div>




<!-- 


<div class="work-experience">
  <ul class="work-exp-list" style="list-style: none; padding-left: 0;">
    {% for job in site.data.work_experience.work_experience %}
    <li class="work-exp-item" style="margin-bottom: 32px;">
      <div class="work-header" style="display: flex; align-items: center; gap: 16px;">
        {% if job.logo %}
          <img src="{{ job.logo }}" alt="{{ job.company }} logo" class="work-logo"
            style="height: 54px; width: 54px; object-fit: contain; margin: 0; display: block;">
        {% endif %}
        <div>
          <h3 style="margin:0 0 2px 0; font-size:1.18em; font-weight: 600; line-height: 1.2;">
            {{ job.position }}
          </h3>
          <span class="work-company" style="font-weight:500;">
            {{ job.company }}
          </span>
          | <span class="work-location" style="color:#444;">
            {{ job.location }}
          </span>
          | <span class="work-dates" style="color:#666; font-size: 0.97em;">
            {{ job.start_date }} – {{ job.end_date }}
          </span>
        </div>
      </div>
      <ul class="work-details" style="margin: 10px 0 6px 0; padding-left: 26px;">
        {% for item in job.description %}
        <li>{{ item }}</li>
        {% endfor %}
      </ul>
      {% if job.skills %}
      <div class="work-skills" style="margin-top: 7px;">
        {% for skill in job.skills %}
        <span class="badge">{{ skill }}</span>
        {% endfor %}
      </div>
      {% endif %}
    </li>
    {% endfor %}
  </ul>
</div>


 -->
