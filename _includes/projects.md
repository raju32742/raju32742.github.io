<h1 id="publications"></h1>

<h2 style="margin: 60px 0px -15px;">
  Research Project 
</h2>

<div class="publications">

  <!-- Conference and Journal Section -->
  <h3 style="margin-top: 40px;">Master's Thesis</h3>
  
 <ol class="bibliography">
  {% assign pubs = site.data.projects.main | where: "category", "ms_thesis" %}
  {% for link in pubs %}
    <li>
      <div class="pub-row">
        <div class="col-sm-3 abbr" style="position: relative; padding-right: 15px; padding-left: 15px;">
          <img src="{{ link.image }}" 
              class="teaser img-fluid z-depth-1 click-to-full" 
              onclick="openFullscreenImage(this)" 
              data-full="{{ link.image }}"
              alt="paper image">
          <abbr class="badge">{{ link.conference_short }}</abbr>
        </div>
        <div class="col-sm-9" style="position: relative; padding-right: 15px; padding-left: 20px;">
          <div class="title"><a href="{{ link.pdf }}">{{ link.title }}</a></div>
          <div class="author">{{ link.authors }}</div>
          <div class="periodical"><em>{{ link.conference }}</em></div>
          <div class="periodical"><em>{{ link.university }}</em></div>
          <div class="supervisor">
            <strong>Supervisor:</strong>
            <a href="{{ link.supervisor_link }}" target="_blank">{{ link.supervisor_name }}</a>
          </div>
          <div class="links">
            {% if link.details_page %}
              <a href="{{ link.details_page }}" class="btn btn-primary" style="font-size:15px; font-weight:700; letter-spacing:0.3px; border-radius:8px; padding: 4px 22px;">
                Details
              </a>
            {% endif %}
          </div>
        </div>
      </div>
    </li>
    <br>
  {% endfor %}
</ol>


 <!-- Conference and Journal Section -->
  <h3 style="margin-top: 20px;">Undergraduate Thesis</h3>
  
 <ol class="bibliography">
  {% assign pubs = site.data.projects.main | where: "category", "bsc_thesis" %}
  {% for link in pubs %}
    <li>
      <div class="pub-row">
        <div class="col-sm-3 abbr" style="position: relative; padding-right: 15px; padding-left: 15px;">
          <img src="{{ link.image }}" 
              class="teaser img-fluid z-depth-1 click-to-full" 
              onclick="openFullscreenImage(this)" 
              data-full="{{ link.image }}"
              alt="paper image">
          <abbr class="badge">{{ link.conference_short }}</abbr>
        </div>
        <div class="col-sm-9" style="position: relative; padding-right: 15px; padding-left: 20px;">
          <div class="title"><a href="{{ link.pdf }}">{{ link.title }}</a></div>
          <div class="author">{{ link.authors }}</div>
          <div class="periodical"><em>{{ link.conference }}</em></div>
          <div class="periodical"><em>{{ link.university }}</em></div>
          <div class="supervisor">
            <strong>Supervisor:</strong>
            <a href="{{ link.supervisor_link }}" target="_blank">{{ link.supervisor_name }}</a>
          </div>
          <div class="links">
            {% if link.details_page %}
              <a href="{{ link.details_page }}" class="btn btn-primary" style="font-size:15px; font-weight:700; letter-spacing:0.3px; border-radius:8px; padding: 4px 22px;">
                Details
              </a>
            {% endif %}
          </div>
        </div>
      </div>
    </li>
    <br>
  {% endfor %}
</ol>


  <!-- Posters/Workshop Section -->
  <h3 style="margin-top: 20px;">Course Projects</h3>
  <ol class="bibliography">
    {% assign pubs = site.data.projects.main | where: "category", "project" %}
    {% for link in pubs %}
      <li>
      <div class="pub-row">
      <div class="col-sm-3 abbr" style="position: relative; padding-right: 15px; padding-left: 15px;">
        <img src="{{ link.image }}" 
            class="teaser img-fluid z-depth-1 click-to-full" 
            onclick="openFullscreenImage(this)" 
            data-full="{{ link.image }}"
            alt="paper image">
        <abbr class="badge">{{ link.conference_short }}</abbr>
      </div>
        <div class="col-sm-9" style="position: relative; padding-right: 15px; padding-left: 20px;">
          <div class="title"><a href="{{ link.pdf }}">{{ link.title }}</a></div>
          <div class="author">{{ link.authors }}</div>
          <div class="periodical"><em>{{ link.conference }}</em></div>
        <div class="links">
          {% if link.pdf %} 
          <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
          {% endif %}
          {% if link.code %} 
          <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
          {% endif %}
          {% if link.page %} 
          <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Presentation</a>
          {% endif %}
          {% if link.data %} 
          <a href="{{ link.data }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Dataset</a>
          {% endif %}
          {% if link.slide %} 
          <a href="{{ link.slide }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Slide</a>
          {% endif %}
        {% if link.bibtex %}
        <a class="btn btn-sm z-depth-0" role="button" style="font-size:12px;" onclick="toggleBibtex('{{ link.bibtex_key }}')">BibTeX</a>
        <div id="bibtex-{{ link.bibtex_key }}" style="display: none; margin-top: 10px;">
        <pre><code class="language-bibtex">{{ link.bibtex }}</code></pre>
        </div>
          {% endif %}
          {% if link.notes %} 
          <strong> <i style="color:#e74d3c; font-weight:600">{{ link.notes }}</i></strong>
          {% endif %}
          {% if link.others %} 
          {{ link.others }}
          {% endif %}
        </div>
      </div>
      </div>
      </li>
      <br>
    {% endfor %}
  </ol>

</div>

<script>
function toggleBibtex(id) {
  const el = document.getElementById('bibtex-' + id);
  el.style.display = el.style.display === "none" ? "block" : "none";
}
</script>

<div id="image-modal" style="display: none; position: fixed; top: 0; left: 0; 
    width: 100vw; height: 100vh; background: rgba(0, 0, 0, 0.85); 
    z-index: 9999; justify-content: center; align-items: center;">
  <img id="modal-img" src="" alt="Zoomed Image" style="max-width: 95%; max-height: 95%; border-radius: 8px; cursor: zoom-out;">
</div>

<script>
function openFullscreenImage(img) {
  const modal = document.getElementById("image-modal");
  const modalImg = document.getElementById("modal-img");
  modalImg.src = img.dataset.full;
  modal.style.display = "flex";
}

document.getElementById("image-modal").addEventListener("click", function () {
  this.style.display = "none";
  document.getElementById("modal-img").src = "";
});
</script>





<!-- <h1 id="publications"></h1>

<h2 style="margin: 60px 0px -15px;">Publications <temp style="font-size:15px;">[</temp><a href="https://scholar.google.ca/citations?user=ToadRS8AAAAJ&hl=en" target="_blank" style="font-size:15px;">Google Scholar</a><temp style="font-size:15px;">]</temp><temp style="font-size:15px;">[</temp><a href="https://orcid.org/my-orcid?orcid=0000-0001-6866-0222" target="_blank" style="font-size:15px;">ORCID</a><temp style="font-size:15px;">]</temp></h2>


<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
<div class="pub-row">
<div class="col-sm-3 abbr" style="position: relative; padding-right: 15px; padding-left: 15px;">
  <img src="{{ link.image }}" 
       class="teaser img-fluid z-depth-1 click-to-full" 
       onclick="openFullscreenImage(this)" 
       data-full="{{ link.image }}"
       alt="paper image">
  <abbr class="badge">{{ link.conference_short }}</abbr>
</div>
     <div class="col-sm-9" style="position: relative; padding-right: 15px; padding-left: 20px;">
      <div class="title"><a href="{{ link.pdf }}">{{ link.title }}</a></div>
      <div class="author">{{ link.authors }}</div>
      <div class="periodical"><em>{{ link.conference }}</em>
      </div>
    <div class="links">
      {% if link.pdf %} 
      <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
      {% endif %}
      {% if link.code %} 
      <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
      {% endif %}
      {% if link.page %} 
      <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Presentation</a>
      {% endif %}
      {% if link.data %} 
      <a href="{{ link.data }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Dataset</a>
      {% endif %}
    {% if link.bibtex %}
    <a class="btn btn-sm z-depth-0" role="button" style="font-size:12px;" onclick="toggleBibtex('{{ link.bibtex_key }}')">BibTeX</a>

  <div id="bibtex-{{ link.bibtex_key }}" style="display: none; margin-top: 10px;">
  <pre><code class="language-bibtex">{{ link.bibtex }}</code></pre>
  </div>
      {% endif %}
      {% if link.notes %} 
      <strong> <i style="color:#e74d3c; font-weight:600">{{ link.notes }}</i></strong>
      {% endif %}
      {% if link.others %} 
      {{ link.others }}
      {% endif %}
    </div>
  </div>
</div>
</li>

<br>

{% endfor %}

<script>
function toggleBibtex(id) {
  const el = document.getElementById('bibtex-' + id);
  el.style.display = el.style.display === "none" ? "block" : "none";
}
</script>


<script>
function toggleZoom(img) {
  img.classList.toggle('zoomed');
}
</script>

<div id="image-modal" style="display: none; position: fixed; top: 0; left: 0; 
    width: 100vw; height: 100vh; background: rgba(0, 0, 0, 0.85); 
    z-index: 9999; justify-content: center; align-items: center;">
  <img id="modal-img" src="" alt="Zoomed Image" style="max-width: 95%; max-height: 95%; border-radius: 8px; cursor: zoom-out;">
</div>

<script>
function openFullscreenImage(img) {
  const modal = document.getElementById("image-modal");
  const modalImg = document.getElementById("modal-img");
  modalImg.src = img.dataset.full;
  modal.style.display = "flex";
}

document.getElementById("image-modal").addEventListener("click", function () {
  this.style.display = "none";
  document.getElementById("modal-img").src = "";
});
</script>
<!-- <li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    <img src="https://img.yliu.me/teaser/MTL_CVPR.png" class="teaser img-fluid z-depth-1">
            <abbr class="badge">CVPR</abbr>
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
      <div class="title"><a href="https://openaccess.thecvf.com/content_CVPR_2019/html/Sun_Meta-Transfer_Learning_for_Few-Shot_Learning_CVPR_2019_paper.html">Meta-Transfer Learning for Few-Shot Learning</a></div>
      <div class="author">Qianru Sun*, <strong>Yaoyao Liu*</strong>, Tat-Seng Chua, Bernt Schiele <br> (* Equal contribution)</div>
      <div class="periodical"><em>IEEE/CVF Conference on Computer Vision and Pattern Recognition <strong>(CVPR)</strong>, 2019.</em>
      </div>
    <div class="links">
      <a href="https://openaccess.thecvf.com/content_CVPR_2019/papers/Sun_Meta-Transfer_Learning_for_Few-Shot_Learning_CVPR_2019_paper.pdf" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
      <a href="https://github.com/yaoyao-liu/meta-transfer-learning" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
      <a href="https://lyy.mpi-inf.mpg.de/mtl/" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
      <a href="https://dblp.uni-trier.de/rec/conf/cvpr/SunLCS19.html?view=bibtex" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
<br>
<strong> <a style="color:#e74d3c; font-weight:600" href="https://scholar.google.com/citations?view_op=view_citation&hl=en&user=Qi2PSmEAAAAJ&authuser=1&citation_for_view=Qi2PSmEAAAAJ:Tyk-4Ss8FVUC"><i id="total_citation_mtl">800+</i><i style="color:#e74d3c; font-weight:600"> Citations • </i></a><a href="https://github.com/yaoyao-liu/meta-transfer-learning" target="_blank" rel="noopener"><i style="color:#e74d3c; font-weight:600" id="githubstars_mtl">600+</i><i style="color:#e74d3c; font-weight:600"> GitHub Stars</i></a></strong>
<br>
<strong><a style="color:#e74d3c; font-weight:600" href="https://scholar.google.com/citations?hl=en&view_op=list_hcore&venue=FXe-a9w0eycJ.2024&vq=en&cstart=60"><i>Top 100 Most Cited CVPR Papers over the Last Five Years</i></a></strong>
  <script>
  githubStars("yaoyao-liu/meta-transfer-learning", function(stars) {
  var startext = document.getElementById("githubstars_mtl");
        startext.innerHTML=stars;
  });
  </script>
  <script>
      $(document).ready(function () {
          
          var gsDataBaseUrl = 'https://raw.githubusercontent.com/yaoyao-liu/yaoyao-liu.github.io/'
          
          $.getJSON(gsDataBaseUrl + "google-scholar-stats/gs_data.json", function (data) {
              var totalCitation = data['publications']['Qi2PSmEAAAAJ:Tyk-4Ss8FVUC']['num_citations']
              document.getElementById('total_citation_mtl').innerHTML = totalCitation;
              var citationEles = document.getElementsByClassName('show_paper_citations')
              Array.prototype.forEach.call(citationEles, element => {
                  var paperId = element.getAttribute('data')
                  var numCitations = data['publications'][paperId]['num_citations']
                  element.innerHTML = '| Citations: ' + numCitations;
              });
          });
      })
  </script>
    </div> 
  </div>
</div>
</li>--
</ol>
</div>
-->
