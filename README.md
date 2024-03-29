# contsys
Formal Ontology for continuity of care based on **International Standard ISO 13940** 

Gulliford et al. (2006) describe “Continuity of care is concerned with the quality of care over time”. There are two aspects of this. One is based on the patient's experience of a 'continuous caring relationship' with the healthcare professional. Another one is based on a system of care where seamless service needed to provide through integration, coordination and interoperable information systems.  

Objectives:
**contsys** OWL ontology
**Define Datatype**
**Test** OWL ontology using real dataset. 


**Update**: Building a Formal Ontology for Continuity of Care **ISO Blog** https://contsys.org/pages/Guest%20blog/FormalOntology 


<!DOCTYPE html>
<html>
<head>
<meta http-equiv="content-type" content="text/html; charset=UTF-8" />
 <link rel="stylesheet" href="resources/primer.css" media="screen" />    <link rel="stylesheet" href="resources/rec.css" media="screen" />    <link rel="stylesheet" href="resources/extra.css" media="screen" />    <link rel="stylesheet" href="resources/owl.css" media="screen" />    <title>Formal Ontology for Continuity of Care</title>


<!-- SCHEMA.ORG METADATA -->
<script type="application/ld+json">{"@context":"https://schema.org","@type":"TechArticle","url":"http://purl.org/net/for-coc","image":"http://vowl.visualdataweb.org/webvowl/#iri=http://purl.org/net/for-coc","name":"Formal Ontology for Continuity of Care", "headline":"A formal ontology of concepts for care process modelling (Contsys). A system of concepts for the continuity of care. A visualisation of a model conforming to International Standard EN ISO 13940:2016.", "datePublished":"Sun Apr 30 17:07:00 CEST 2023", "license":"https://creativecommons.org/licenses/by-sa/4.0/", "author":[{"@type":"Person","name":"Subhashis Das"}], "contributor":[{"@type":"Person","name":"Pamela Hussey"}]}</script>

<script src="resources/jquery.js"></script> 
<script src="resources/marked.min.js"></script> 
    <script> 
function loadHash() {
  jQuery(".markdown").each(function(el){jQuery(this).after(marked(jQuery(this).text())).remove()});
   var hash = location.hash;
   if($(hash).offset()!=null){
     $('html, body').animate({scrollTop: $(hash).offset().top}, 0);
}
   loadTOC();
}
function loadTOC(){
   //process toc dynamically
     var t='<h2>Table of contents</h2><ul>';i = 1;j=0;
     jQuery(".list").each(function(){
      if(jQuery(this).is('h2')){
         if(j>0){
            t+='</ul>';
            j=0;
         }
         t+= '<li>'+i+'. <a href=#'+ jQuery(this).attr('id')+'>'+ jQuery(this).ignore("span").text()+'</a></li>';
         i++;
      }
      if(jQuery(this).is('h3')){
         if(j==0){
            t+='<ul>';
         }
         j++;
         t+= '<li>'+(i-1)+'.'+j+'. '+'<a href=#'+ jQuery(this).attr('id')+'>'+ jQuery(this).ignore("span").text()+'</a></li>';
      }
     });
     t+='</ul>';
     $("#toc").html(t); 
}
$(function(){
    loadHash();
}); $.fn.ignore = function(sel){
        return this.clone().find(sel||">*").remove().end();
 }; 
   </script> 
  </head> 

<body>
<div class="container">
<div class="head">
<div style="float:right">language <a href="index-en.html"><b>en</b></a> </div>
<h1>Formal Ontology for Continuity of Care</h1>


<dl>
<dt>Latest version:</dt>
<dd><a href="http://purl.org/net/for-coc">http://purl.org/net/for-coc</a></dd>
<dt>Authors:</dt>
<dd>Subhashis Das</dd>

<dt>Contributors:</dt>
<dd>Pamela Hussey</dd>

<dt>Download serialization:</dt><dd><span><a href="ontology.json" target="_blank"><img src="https://img.shields.io/badge/Format-JSON_LD-blue.svg" alt="JSON-LD" /></a> </span><span><a href="ontology.xml" target="_blank"><img src="https://img.shields.io/badge/Format-RDF/XML-blue.svg" alt="RDF/XML" /></a> </span><span><a href="ontology.nt" target="_blank"><img src="https://img.shields.io/badge/Format-N_Triples-blue.svg" alt="N-Triples" /></a> </span><span><a href="ontology.ttl" target="_blank"><img src="https://img.shields.io/badge/Format-TTL-blue.svg" alt="TTL" /></a> </span></dd><dt>License: </dt><dd><a href="https://creativecommons.org/licenses/by-sa/4.0/" target="_blank"><img src="https://img.shields.io/badge/License-https://creativecommons.org/licenses/by_sa/4.0/-blue.svg" alt="https://creativecommons.org/licenses/by-sa/4.0/" /></a>
</dd><dt>Visualization:</dt><dd><a href="webvowl/index.html#" target="_blank"><img src="https://img.shields.io/badge/Visualize_with-WebVowl-blue.svg" alt="Visualize with WebVowl" /></a></dd>
<!-- <dt>Evaluation:</dt><dd><a href="OOPSEvaluation/OOPSeval.html#" target="_blank"><img src="https://img.shields.io/badge/Evaluate_with-OOPS! (OntOlogy Pitfall Scanner!)-blue.svg" alt="Evaluate with OOPS!" /></a></dd> --><dt>Cite as:</dt>
<dd>Subhashis Das. Formal Ontology for Continuity of Care.</dd>
</dl>

<a href="provenance/provenance-en.html" target="_blank">Provenance of this page</a><hr/>
</div>
<div class="status">
<div>
<span>Ontology Specification Draft</span>
</div>
</div>     <div id="abstract"><h2>Abstract</h2><span class="markdown">
A formal ontology of concepts for care process modelling (Contsys). A system of concepts for the continuity of care. A visualisation of a model conforming to International Standard EN ISO 13940:2016.</span>
</div>
<div id="toc"></div> 

<!--INTRODUCTION SECTION-->
    <div id="introduction"><h2 id="intro" class="list">Introduction <span class="backlink"> back to <a href="#toc">ToC</a></span></h2>
<span class="markdown">
This is a place holder text for the introduction. The introduction should briefly describe the ontology, its motivation, state of the art and goals.</span>
<div id="namespacedeclarations">
<h3 id="ns" class="list">Namespace declarations</h3>
<div id="ns" align="center">
<table>
<caption> <a href="#ns"> Table 1</a>: Namespaces used in the document </caption>
<tbody>
<tr><td><b>[Ontology NS Prefix]</b></td><td>&lt;http://purl.org/net/for-coc&gt;</td></tr>
<tr><td><b>ConC</b></td><td>&lt;http://purl.org/net/swbp-vm/CoC&gt;</td></tr>
<tr><td><b>fhir</b></td><td>&lt;http://hl7.org/fhir&gt;</td></tr>
<tr><td><b>for-cocd-ontology-781</b></td><td>&lt;http://purl.org/net/for-cocd-ontology-781&gt;</td></tr>
<tr><td><b>owl</b></td><td>&lt;http://www.w3.org/2002/07/owl&gt;</td></tr>
<tr><td><b>oboInOwl</b></td><td>&lt;http://www.geneontology.org/formats/oboInOwl&gt;</td></tr>
<tr><td><b>concept</b></td><td>&lt;https://contsys.org/concept&gt;</td></tr>
<tr><td><b>DnS</b></td><td>&lt;http://www.loa-cnr.it/ontologies/DnS&gt;</td></tr>
<tr><td><b>xsd</b></td><td>&lt;http://www.w3.org/2001/XMLSchema&gt;</td></tr>
<tr><td><b>skos</b></td><td>&lt;http://www.w3.org/2004/02/skos/core&gt;</td></tr>
<tr><td><b>rdfs</b></td><td>&lt;http://www.w3.org/2000/01/rdf-schema&gt;</td></tr>
<tr><td><b>DOLCE-Lite</b></td><td>&lt;http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite&gt;</td></tr>
<tr><td><b>rdf</b></td><td>&lt;http://www.w3.org/1999/02/22-rdf-syntax-ns&gt;</td></tr>
<tr><td><b>terms</b></td><td>&lt;http://purl.org/dc/terms&gt;</td></tr>
<tr><td><b>CoC</b></td><td>&lt;http://purl.org/net/swbp-vm/CoC&gt;</td></tr>
<tr><td><b>xml</b></td><td>&lt;http://www.w3.org/XML/1998/namespace&gt;</td></tr>
<tr><td><b>dc</b></td><td>&lt;http://purl.org/dc/elements/1.1&gt;</td></tr>
</tbody>
</table>
</div>
</div>
</div>
  

<!--OVERVIEW SECTION-->
    <div id="overview"><h2 id="overv" class="list">Formal Ontology for Continuity of Care: Overview <span class="backlink"> back to <a href="#toc">ToC</a></span></h2>
<span class="markdown">
This ontology has the following classes and properties.</span>
<h4>Classes</h4>
<ul xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" class="hlist">
   <li>
      <a href="#https://contsys.org/concept/adverse_event_management"
         title="https://contsys.org/concept/adverse_event_management">
         <span>adverse event management</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/adverse_event" title="https://contsys.org/concept/adverse_event">adverseEvent</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/appointment" title="https://contsys.org/concept/appointment">appointment</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/authorization_by_law"
         title="https://contsys.org/concept/authorization_by_law">
         <span>authorization by law</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/automated_healthcare"
         title="https://contsys.org/concept/automated_healthcare">automatedHealthcare</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/automatic_medical_device"
         title="https://contsys.org/concept/automatic_medical_device">
         <span>automatic medical device</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/care_period_mandate" title="https://contsys.org/concept/care_period_mandate">
         <span>care period mandate</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/care_plan" title="https://contsys.org/concept/care_plan">
         <span>care plan</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/certificate_related_to_a_healthcare_matter"
         title="https://contsys.org/concept/certificate_related_to_a_healthcare_matter">
         <span>certificate related to a healthcare matter</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/clinical_guideline" title="https://contsys.org/concept/clinical_guideline">
         <span>clinical guideline</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/clinical_pathway" title="https://contsys.org/concept/clinical_pathway">
         <span>clinical pathway</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/clinical_process_episode"
         title="https://contsys.org/concept/clinical_process_episode">
         <span>clinical process episode</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/clinical_process_interest"
         title="https://contsys.org/concept/clinical_process_interest">
         <span>clinical process interest</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/clinical_process_outcome_evaluation"
         title="https://contsys.org/concept/clinical_process_outcome_evaluation">
         <span>clinical process outcome evaluation</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/clinical_report" title="https://contsys.org/concept/clinical_report">
         <span>clinical report</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/clinical_process" title="https://contsys.org/concept/clinical_process">clinicalProcess</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/consent_competence" title="https://contsys.org/concept/consent_competence">
         <span>consent competence</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/considered_condition"
         title="https://contsys.org/concept/considered_condition">
         <span>considered condition</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/contact" title="https://contsys.org/concept/contact">contact</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/contact_period" title="https://contsys.org/concept/contact_period">
         <span>contact period</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/continuity_facilitator_mandate"
         title="https://contsys.org/concept/continuity_facilitator_mandate">
         <span>continuity facilitator mandate</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/core_care_plan" title="https://contsys.org/concept/core_care_plan">
         <span>core care plan</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/data_repository" title="https://contsys.org/concept/data_repository">
         <span>data repository</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/demand_for_initial_contact"
         title="https://contsys.org/concept/demand_for_initial_contact">
         <span>demand for initial contact</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/demand_mandate" title="https://contsys.org/concept/demand_mandate">
         <span>demand mandate</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/demand_for_care" title="https://contsys.org/concept/demand_for_care">demandForCare</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/discharge_report" title="https://contsys.org/concept/discharge_report">
         <span>discharge report</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/discharge_summary" title="https://contsys.org/concept/discharge_summary">
         <span>discharge summary</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/dissent" title="https://contsys.org/concept/dissent">
         <span>dissent</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/electronic_health_record_component"
         title="https://contsys.org/concept/electronic_health_record_component">
         <span>electronic health record component</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/electronic_health_record_extract"
         title="https://contsys.org/concept/electronic_health_record_extract">
         <span>electronic health record extract</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/electronic_patient_summary"
         title="https://contsys.org/concept/electronic_patient_summary">
         <span>electronic patient summary</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/episode_of_care" title="https://contsys.org/concept/episode_of_care">
         <span>episode of care</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/episodes_of_care_bundle"
         title="https://contsys.org/concept/episodes_of_care_bundle">
         <span>episodes of care bundle</span>
      </a>
   </li>
   <li>
      <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
         title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/excluded_condition" title="https://contsys.org/concept/excluded_condition">
         <span>excluded condition</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_approach" title="https://contsys.org/concept/health_approach">
         <span>health approach</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_concern" title="https://contsys.org/concept/health_concern">
         <span>health concern</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_condition" title="https://contsys.org/concept/health_condition">
         <span>health condition</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_condition_delay"
         title="https://contsys.org/concept/health_condition_delay">
         <span>health condition delay</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_condition_evolution"
         title="https://contsys.org/concept/health_condition_evolution">
         <span>health condition evolution</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_condition_period"
         title="https://contsys.org/concept/health_condition_period">
         <span>health condition period</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_issue" title="https://contsys.org/concept/health_issue">
         <span>health issue</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_need" title="https://contsys.org/concept/health_need">
         <span>health need</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_objective" title="https://contsys.org/concept/health_objective">
         <span>health objective</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_problem" title="https://contsys.org/concept/health_problem">
         <span>health problem</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_problem_list" title="https://contsys.org/concept/health_problem_list">
         <span>health problem list</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_record" title="https://contsys.org/concept/health_record">
         <span>health record</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_record_component"
         title="https://contsys.org/concept/health_record_component">
         <span>health record component</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_record_extract"
         title="https://contsys.org/concept/health_record_extract">
         <span>health record extract</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_state" title="https://contsys.org/concept/health_state">
         <span>health state</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_thread" title="https://contsys.org/concept/health_thread">
         <span>health thread</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare" title="https://contsys.org/concept/healthcare">healthcare</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_activities_bundle"
         title="https://contsys.org/concept/healthcare_activities_bundle">
         <span>healthcare activities bundle</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_activity_delay"
         title="https://contsys.org/concept/healthcare_activity_delay">
         <span>healthcare activity delay</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_activity_directory"
         title="https://contsys.org/concept/healthcare_activity_directory">
         <span>healthcare activity directory</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_activity_element"
         title="https://contsys.org/concept/healthcare_activity_element">
         <span>healthcare activity element</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_activity_management"
         title="https://contsys.org/concept/healthcare_activity_management">
         <span>healthcare activity management</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_activity_mandate"
         title="https://contsys.org/concept/healthcare_activity_mandate">
         <span>healthcare activity mandate</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_activity_period"
         title="https://contsys.org/concept/healthcare_activity_period">
         <span>healthcare activity period</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_activity_period_element"
         title="https://contsys.org/concept/healthcare_activity_period_element">
         <span>healthcare activity period element</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_actor" title="https://contsys.org/concept/healthcare_actor">
         <span>healthcare actor</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_administration"
         title="https://contsys.org/concept/healthcare_administration">
         <span>healthcare administration</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_assessment"
         title="https://contsys.org/concept/healthcare_assessment">
         <span>healthcare assessment</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_communication"
         title="https://contsys.org/concept/healthcare_communication">
         <span>healthcare communication</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_documenting"
         title="https://contsys.org/concept/healthcare_documenting">
         <span>healthcare documenting</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_evaluation"
         title="https://contsys.org/concept/healthcare_evaluation">
         <span>healthcare evaluation</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_funds" title="https://contsys.org/concept/healthcare_funds">
         <span>healthcare funds</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_goal" title="https://contsys.org/concept/healthcare_goal">
         <span>healthcare goal</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_information"
         title="https://contsys.org/concept/healthcare_information">
         <span>healthcare information</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_information_for_import"
         title="https://contsys.org/concept/healthcare_information_for_import">
         <span>healthcare information for import</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_investigation"
         title="https://contsys.org/concept/healthcare_investigation">
         <span>healthcare investigation</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_mandate" title="https://contsys.org/concept/healthcare_mandate">
         <span>healthcare mandate</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_matter" title="https://contsys.org/concept/healthcare_matter">
         <span>healthcare matter</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_needs_assessment"
         title="https://contsys.org/concept/healthcare_needs_assessment">
         <span>healthcare needs assessment</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_personnel"
         title="https://contsys.org/concept/healthcare_personnel">
         <span>healthcare personnel</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_planning" title="https://contsys.org/concept/healthcare_planning">
         <span>healthcare planning</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_process_evaluation"
         title="https://contsys.org/concept/healthcare_process_evaluation">
         <span>healthcare process evaluation</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_professional"
         title="https://contsys.org/concept/healthcare_professional">
         <span>healthcare professional</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_professional_entitlement"
         title="https://contsys.org/concept/healthcare_professional_entitlement">
         <span>healthcare professional entitlement</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_provider" title="https://contsys.org/concept/healthcare_provider">
         <span>healthcare provider</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_provider_activity"
         title="https://contsys.org/concept/healthcare_provider_activity">
         <span>healthcare provider activity</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_quality_management"
         title="https://contsys.org/concept/healthcare_quality_management">
         <span>healthcare quality management</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_resource" title="https://contsys.org/concept/healthcare_resource">
         <span>healthcare resource</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_resource_management"
         title="https://contsys.org/concept/healthcare_resource_management">
         <span>healthcare resource management</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_supporting_organization"
         title="https://contsys.org/concept/healthcare_supporting_organization">
         <span>healthcare supporting organization</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_third_party"
         title="https://contsys.org/concept/healthcare_third_party">
         <span>healthcare third party</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_third_party_activity"
         title="https://contsys.org/concept/healthcare_third_party_activity">
         <span>healthcare third party activity</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_treatment"
         title="https://contsys.org/concept/healthcare_treatment">
         <span>healthcare treatment</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_service_directory"
         title="https://contsys.org/concept/healthcare_service_directory">healthcare_service_directory</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_activity" title="https://contsys.org/concept/healthcare_activity">healthcareActivity</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_appointment"
         title="https://contsys.org/concept/healthcare_appointment">healthcareAppoinment</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_commitment"
         title="https://contsys.org/concept/healthcare_commitment">healthcareCommitment</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_information_request"
         title="https://contsys.org/concept/healthcare_information_request">healthcareInformationRequest</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_organization"
         title="https://contsys.org/concept/healthcare_organization">healthcareOrganization</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_process" title="https://contsys.org/concept/healthcare_process">healthcareProcess</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/healthcare_service" title="https://contsys.org/concept/healthcare_service">healthcareService</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/health_related_period"
         title="https://contsys.org/concept/health_related_period">healthRelatedPeriod</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/informed_consent" title="https://contsys.org/concept/informed_consent">
         <span>informed consent</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/initial_contact" title="https://contsys.org/concept/initial_contact">initialContact</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/input_health_state" title="https://contsys.org/concept/input_health_state">
         <span>input health state</span>
      </a>
   </li>
   <li>
      <a href="#location" title="http://purl.org/net/for-coc#location">
         <span>location</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/mandate_to_export_personal_information"
         title="https://contsys.org/concept/mandate_to_export_personal_information">
         <span>mandate to export personal information</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/mandated_period_of_care"
         title="https://contsys.org/concept/mandated_period_of_care">
         <span>mandated period of care</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/medical_device" title="https://contsys.org/concept/medical_device">medicalDevice</a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/MedicationRequest" title="http://hl7.org/fhir/MedicationRequest">
         <span>medication request</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/medicinal_product" title="https://contsys.org/concept/medicinal_product">
         <span>medicinal product</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/medium" title="https://contsys.org/concept/medium">
         <span>medium</span>
      </a>
   </li>
   <li>
      <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
         title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/multi-professional_care_plan"
         title="https://contsys.org/concept/multi-professional_care_plan">
         <span>multi professional care plan</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/needed_healthcare_activity"
         title="https://contsys.org/concept/needed_healthcare_activity">
         <span>needed healthcare activity</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/next_of_kin" title="https://contsys.org/concept/next_of_kin">
         <span>next of kin</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/non-ratified_healthcare_information"
         title="https://contsys.org/concept/non-ratified_healthcare_information">
         <span>non ratified healthcare information</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/observed_condition" title="https://contsys.org/concept/observed_condition">
         <span>observed condition</span>
      </a>
   </li>
   <li>
      <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Organization"
         title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Organization">organization</a>
   </li>
   <li>
      <a href="#d-ontology-781#organizationRole"
         title="http://purl.org/net/for-cocd-ontology-781#organizationRole">
         <span>organization role</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/other_carer" title="https://contsys.org/concept/other_carer">
         <span>other carer</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/output_health_state" title="https://contsys.org/concept/output_health_state">
         <span>output health state</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/party" title="https://contsys.org/concept/party">
         <span>party</span>
      </a>
   </li>
   <li>
      <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Natural-Person"
         title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Natural-Person">person</a>
   </li>
   <li>
      <a href="#d-ontology-781#personRole"
         title="http://purl.org/net/for-cocd-ontology-781#personRole">
         <span>person role</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/personal_health_record"
         title="https://contsys.org/concept/personal_health_record">
         <span>personal health record</span>
      </a>
   </li>
   <li>
      <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object"
         title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object">physicalObject</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/potential_health_condition"
         title="https://contsys.org/concept/potential_health_condition">
         <span>potential health condition</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/prescribed_self-care"
         title="https://contsys.org/concept/prescribed_self-care">
         <span>prescribed self care</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/prescribed_third_party_activity"
         title="https://contsys.org/concept/prescribed_third_party_activity">
         <span>prescribed third party activity</span>
      </a>
   </li>
   <li>
      <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Process"
         title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Process">process</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/product" title="https://contsys.org/concept/product">
         <span>product</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/professional_health_record"
         title="https://contsys.org/concept/professional_health_record">
         <span>professional health record</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/professionally_assessed_condition"
         title="https://contsys.org/concept/professionally_assessed_condition">
         <span>professionally assessed condition</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/prognostic_condition"
         title="https://contsys.org/concept/prognostic_condition">
         <span>prognostic condition</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/protocol" title="https://contsys.org/concept/protocol">
         <span>protocol</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/reason_for_demand_for_care"
         title="https://contsys.org/concept/reason_for_demand_for_care">
         <span>reason for demand for care</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/referral" title="https://contsys.org/concept/referral">referral</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/request" title="https://contsys.org/concept/request">request</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/resource" title="https://contsys.org/concept/resource">
         <span>resource</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/resource_delay" title="https://contsys.org/concept/resource_delay">
         <span>resource delay</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/resultant_condition" title="https://contsys.org/concept/resultant_condition">
         <span>resultant condition</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/risk_condition" title="https://contsys.org/concept/risk_condition">
         <span>risk condition</span>
      </a>
   </li>
   <li>
      <a href="#http://www.loa-cnr.it/ontologies/DnS#role" title="http://www.loa-cnr.it/ontologies/DnS#role">role</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/self-care_period" title="https://contsys.org/concept/self-care_period">
         <span>self care period</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/self-care_activity" title="https://contsys.org/concept/self-care_activity">selfCareActivity</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/service" title="https://contsys.org/concept/service">
         <span>service</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/sharable_data_repository"
         title="https://contsys.org/concept/sharable_data_repository">
         <span>sharable data repository</span>
      </a>
   </li>
   <li>
      <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State"
         title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State">state</a>
   </li>
   <li>
      <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Stative"
         title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Stative">stative</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/subject_of_care_desire"
         title="https://contsys.org/concept/subject_of_care_desire">
         <span>subject of care desire</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/subject_of_care_preference_delay"
         title="https://contsys.org/concept/subject_of_care_preference_delay">
         <span>subject of care preference delay</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/subject_of_care_proxy"
         title="https://contsys.org/concept/subject_of_care_proxy">
         <span>subject of care proxy</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/subject_of_care" title="https://contsys.org/concept/subject_of_care">subjectOfCare</a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/summarized_healthcare_information_repository"
         title="https://contsys.org/concept/summarized_healthcare_information_repository">
         <span>summarized healthcare information repository</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/target_condition" title="https://contsys.org/concept/target_condition">
         <span>target condition</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/uniprofessional_care_plan"
         title="https://contsys.org/concept/uniprofessional_care_plan">
         <span>uniprofessional care plan</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/working_diagnosis" title="https://contsys.org/concept/working_diagnosis">
         <span>working diagnosis</span>
      </a>
   </li>
</ul><h4>Object Properties</h4><ul xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" class="hlist">
   <li>
      <a href="#componentOf" title="http://purl.org/net/for-coc#componentOf">
         <span>component of</span>
      </a>
   </li>
   <li>
      <a href="#controlsQualityOf" title="http://purl.org/net/for-coc#controlsQualityOf">
         <span>controls quality of</span>
      </a>
   </li>
   <li>
      <a href="#derivesFrom" title="http://purl.org/net/for-coc#derivesFrom">
         <span>derives from</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/MedicationRequest.subject.Reference"
         title="http://hl7.org/fhir/MedicationRequest.subject.Reference">
         <span>medication request.subject. reference</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Observation.basedOn" title="http://hl7.org/fhir/Observation.basedOn">
         <span>observation.based on</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Observation.encounter" title="http://hl7.org/fhir/Observation.encounter">
         <span>observation.encounter</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Observation.performer" title="http://hl7.org/fhir/Observation.performer">
         <span>observation.performer</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Observation.subject" title="http://hl7.org/fhir/Observation.subject">
         <span>observation.subject</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/patient.address.city" title="http://hl7.org/fhir/patient.address.city">
         <span>patient.address.city</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/patient.address.country" title="http://hl7.org/fhir/patient.address.country">
         <span>patient.address.country</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/patient.address.district" title="http://hl7.org/fhir/patient.address.district">
         <span>patient.address.district</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/patient.contact.address.city" title="http://hl7.org/fhir/patient.contact.address.city">
         <span>patient.contact.address.city</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/patient.contact.address.country"
         title="http://hl7.org/fhir/patient.contact.address.country">
         <span>patient.contact.address.country</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/patient.contact.address.district"
         title="http://hl7.org/fhir/patient.contact.address.district">
         <span>patient.contact.address.district</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Patient.contact.organization" title="http://hl7.org/fhir/Patient.contact.organization">
         <span>patient.contact.organization</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/patient.generalpractitioner" title="http://hl7.org/fhir/patient.generalpractitioner">
         <span>patient.generalpractitioner</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Patient.managingOrganization" title="http://hl7.org/fhir/Patient.managingOrganization">
         <span>patient.managing organization</span>
      </a>
   </li>
   <li>
      <a href="#seeksToReceive" title="http://purl.org/net/for-coc#seeksToReceive">
         <span>seeks to receive</span>
      </a>
   </li>
</ul><h4>Data Properties</h4><ul xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" class="hlist">
   <li>
      <a href="#https://contsys.org/concept/attachment_value" title="https://contsys.org/concept/attachment_value">
         <span>attachment value</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/attestation_information"
         title="https://contsys.org/concept/attestation_information">
         <span>attestation information</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/base_component" title="https://contsys.org/concept/base_component">
         <span>base component</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/coded_simple_value" title="https://contsys.org/concept/coded_simple_value">
         <span>coded simple value</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/coded_value" title="https://contsys.org/concept/coded_value">
         <span>coded value</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/duration_value" title="https://contsys.org/concept/duration_value">
         <span>duration value</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/MedicationRequest.courseOfTherapyType"
         title="http://hl7.org/fhir/MedicationRequest.courseOfTherapyType">
         <span>medication request.course of therapy type</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/MedicationRequest.dispenseRequest.dispenseInterval"
         title="http://hl7.org/fhir/MedicationRequest.dispenseRequest.dispenseInterval">
         <span>medication request.dispense request.dispense interval</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/MedicationRequest.dispenseRequest.expectedSupplyDuration"
         title="http://hl7.org/fhir/MedicationRequest.dispenseRequest.expectedSupplyDuration">
         <span>medication request.dispense request.expected supply duration</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/MedicationRequest.dispenseRequest.initialFill.Duration"
         title="http://hl7.org/fhir/MedicationRequest.dispenseRequest.initialFill.Duration">
         <span>medication request.dispense request.initial fill. duration</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/MedicationRequest.dispenseRequest.initialFill.quantity"
         title="http://hl7.org/fhir/MedicationRequest.dispenseRequest.initialFill.quantity">
         <span>medication request.dispense request.initial fill.quantity</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/MedicationRequest.dispenseRequest.numberOfRepeatsAllowed"
         title="http://hl7.org/fhir/MedicationRequest.dispenseRequest.numberOfRepeatsAllowed">
         <span>medication request.dispense request.number of repeats allowed</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/MedicationRequest.dispenseRequest.quantity"
         title="http://hl7.org/fhir/MedicationRequest.dispenseRequest.quantity">
         <span>medication request.dispense request.quantity</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/MedicationRequest.dispenseRequest.validityPeriod"
         title="http://hl7.org/fhir/MedicationRequest.dispenseRequest.validityPeriod">
         <span>medication request.dispense request.validity period</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/MedicationRequest.note" title="http://hl7.org/fhir/MedicationRequest.note">
         <span>medication request.note</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/MedicationRequest.status" title="http://hl7.org/fhir/MedicationRequest.status">
         <span>medication request.status</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/MedicationRequest.statusReason"
         title="http://hl7.org/fhir/MedicationRequest.statusReason">
         <span>medication request.status reason</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Observation.code" title="http://hl7.org/fhir/Observation.code">
         <span>observation.code</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Observation.effectiveDateTime"
         title="http://hl7.org/fhir/Observation.effectiveDateTime">
         <span>observation.effective date time</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Observation.identifier" title="http://hl7.org/fhir/Observation.identifier">
         <span>observation.identifier</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Observation.method" title="http://hl7.org/fhir/Observation.method">
         <span>observation.method</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Observation.status" title="http://hl7.org/fhir/Observation.status">
         <span>observation.status</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Observation.value" title="http://hl7.org/fhir/Observation.value">
         <span>observation.value</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Patient.active" title="http://hl7.org/fhir/Patient.active">
         <span>patient.active</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Patient.address.line" title="http://hl7.org/fhir/Patient.address.line">
         <span>patient.address.line</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Patient.communication.language"
         title="http://hl7.org/fhir/Patient.communication.language">
         <span>patient.communication.language</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Patient.contact.address.postalcode"
         title="http://hl7.org/fhir/Patient.contact.address.postalcode">
         <span>patient.contact.address.postalcode</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Patient.contact.gender" title="http://hl7.org/fhir/Patient.contact.gender">
         <span>patient.contact.gender</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Patient.contact.name" title="http://hl7.org/fhir/Patient.contact.name">
         <span>patient.contact.name</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Patient.forename" title="http://hl7.org/fhir/Patient.forename">
         <span>patient.forename</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Patient.gender" title="http://hl7.org/fhir/Patient.gender">
         <span>patient.gender</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Patient.photo" title="http://hl7.org/fhir/Patient.photo">
         <span>patient.photo</span>
      </a>
   </li>
   <li>
      <a href="#http://hl7.org/fhir/Patient.surname" title="http://hl7.org/fhir/Patient.surname">
         <span>patient.surname</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/physical_quantity_value"
         title="https://contsys.org/concept/physical_quantity_value">
         <span>physical quantity value</span>
      </a>
   </li>
   <li>
      <a href="#https://contsys.org/concept/point_in_time_value" title="https://contsys.org/concept/point_in_time_value">
         <span>point in time value</span>
      </a>
   </li>
</ul><h4>Annotation Properties</h4><ul xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" class="hlist">
   <li>
      <a href="#http://purl.org/dc/elements/1.1/contributor" title="http://purl.org/dc/elements/1.1/contributor">
         <span>contributor</span>
      </a>
   </li>
   <li>
      <a href="#http://purl.org/dc/elements/1.1/creator" title="http://purl.org/dc/elements/1.1/creator">
         <span>creator</span>
      </a>
   </li>
   <li>
      <a href="#http://www.geneontology.org/formats/oboInOwl#hasDbXref"
         title="http://www.geneontology.org/formats/oboInOwl#hasDbXref">database_cross_reference</a>
   </li>
   <li>
      <a href="#http://purl.org/dc/elements/1.1/date" title="http://purl.org/dc/elements/1.1/date">
         <span>date</span>
      </a>
   </li>
   <li>
      <a href="#http://www.w3.org/2004/02/skos/core#example" title="http://www.w3.org/2004/02/skos/core#example">
         <span>example</span>
      </a>
   </li>
   <li>
      <a href="#http://purl.org/dc/terms/license" title="http://purl.org/dc/terms/license">
         <span>license</span>
      </a>
   </li>
   <li>
      <a href="#http://www.w3.org/2004/02/skos/core#note" title="http://www.w3.org/2004/02/skos/core#note">
         <span>note</span>
      </a>
   </li>
   <li>
      <a href="#http://purl.org/dc/elements/1.1/title" title="http://purl.org/dc/elements/1.1/title">
         <span>title</span>
      </a>
   </li>
</ul><h4>Named Individuals</h4><ul xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" class="hlist">
   <li>
      <a href="#patient1" title="http://purl.org/net/for-coc#patient1">
         <span>patient1</span>
      </a>
   </li>
</ul><iframe align="center" width="100%" height ="500px" src="webvowl/index.html"></iframe> 
</div>
  

<!--DESCRIPTION SECTION-->
    <div id="description"><h2 id="desc" class="list">Formal Ontology for Continuity of Care: Description <span class="backlink"> back to <a href="#toc">ToC</a></span></h2>
<span class="markdown">
This is a placeholder text for the description of your ontology. The description should include an explanation and a diagram explaining how the classes are related, examples of usage, etc.</span>

</div>
   

<!--CROSSREF SECTION-->
   <div id="crossref"><h2 id="crossreference" class="list">Cross reference for Formal Ontology for Continuity of Care classes, properties and dataproperties <span class="backlink"> back to <a href="#toc">ToC</a></span></h2>
This section provides details for each class and property defined by Formal Ontology for Continuity of Care.
<div xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="classes">
   <h3 id="classes-headline" class="list">Classes</h3>
   <ul class="hlist">
      <li>
         <a href="#https://contsys.org/concept/adverse_event_management"
            title="https://contsys.org/concept/adverse_event_management">
            <span>adverse event management</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/adverse_event" title="https://contsys.org/concept/adverse_event">adverseEvent</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/appointment" title="https://contsys.org/concept/appointment">appointment</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/authorization_by_law"
            title="https://contsys.org/concept/authorization_by_law">
            <span>authorization by law</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/automated_healthcare"
            title="https://contsys.org/concept/automated_healthcare">automatedHealthcare</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/automatic_medical_device"
            title="https://contsys.org/concept/automatic_medical_device">
            <span>automatic medical device</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/care_period_mandate" title="https://contsys.org/concept/care_period_mandate">
            <span>care period mandate</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/care_plan" title="https://contsys.org/concept/care_plan">
            <span>care plan</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/certificate_related_to_a_healthcare_matter"
            title="https://contsys.org/concept/certificate_related_to_a_healthcare_matter">
            <span>certificate related to a healthcare matter</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/clinical_guideline" title="https://contsys.org/concept/clinical_guideline">
            <span>clinical guideline</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/clinical_pathway" title="https://contsys.org/concept/clinical_pathway">
            <span>clinical pathway</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/clinical_process_episode"
            title="https://contsys.org/concept/clinical_process_episode">
            <span>clinical process episode</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/clinical_process_interest"
            title="https://contsys.org/concept/clinical_process_interest">
            <span>clinical process interest</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/clinical_process_outcome_evaluation"
            title="https://contsys.org/concept/clinical_process_outcome_evaluation">
            <span>clinical process outcome evaluation</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/clinical_report" title="https://contsys.org/concept/clinical_report">
            <span>clinical report</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/clinical_process" title="https://contsys.org/concept/clinical_process">clinicalProcess</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/consent_competence" title="https://contsys.org/concept/consent_competence">
            <span>consent competence</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/considered_condition"
            title="https://contsys.org/concept/considered_condition">
            <span>considered condition</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/contact" title="https://contsys.org/concept/contact">contact</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/contact_period" title="https://contsys.org/concept/contact_period">
            <span>contact period</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/continuity_facilitator_mandate"
            title="https://contsys.org/concept/continuity_facilitator_mandate">
            <span>continuity facilitator mandate</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/core_care_plan" title="https://contsys.org/concept/core_care_plan">
            <span>core care plan</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/data_repository" title="https://contsys.org/concept/data_repository">
            <span>data repository</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/demand_for_initial_contact"
            title="https://contsys.org/concept/demand_for_initial_contact">
            <span>demand for initial contact</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/demand_mandate" title="https://contsys.org/concept/demand_mandate">
            <span>demand mandate</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/demand_for_care" title="https://contsys.org/concept/demand_for_care">demandForCare</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/discharge_report" title="https://contsys.org/concept/discharge_report">
            <span>discharge report</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/discharge_summary" title="https://contsys.org/concept/discharge_summary">
            <span>discharge summary</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/dissent" title="https://contsys.org/concept/dissent">
            <span>dissent</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/electronic_health_record_component"
            title="https://contsys.org/concept/electronic_health_record_component">
            <span>electronic health record component</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/electronic_health_record_extract"
            title="https://contsys.org/concept/electronic_health_record_extract">
            <span>electronic health record extract</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/electronic_patient_summary"
            title="https://contsys.org/concept/electronic_patient_summary">
            <span>electronic patient summary</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/episode_of_care" title="https://contsys.org/concept/episode_of_care">
            <span>episode of care</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/episodes_of_care_bundle"
            title="https://contsys.org/concept/episodes_of_care_bundle">
            <span>episodes of care bundle</span>
         </a>
      </li>
      <li>
         <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
            title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/excluded_condition" title="https://contsys.org/concept/excluded_condition">
            <span>excluded condition</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_approach" title="https://contsys.org/concept/health_approach">
            <span>health approach</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_concern" title="https://contsys.org/concept/health_concern">
            <span>health concern</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_condition" title="https://contsys.org/concept/health_condition">
            <span>health condition</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_condition_delay"
            title="https://contsys.org/concept/health_condition_delay">
            <span>health condition delay</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_condition_evolution"
            title="https://contsys.org/concept/health_condition_evolution">
            <span>health condition evolution</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_condition_period"
            title="https://contsys.org/concept/health_condition_period">
            <span>health condition period</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_issue" title="https://contsys.org/concept/health_issue">
            <span>health issue</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_need" title="https://contsys.org/concept/health_need">
            <span>health need</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_objective" title="https://contsys.org/concept/health_objective">
            <span>health objective</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_problem" title="https://contsys.org/concept/health_problem">
            <span>health problem</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_problem_list" title="https://contsys.org/concept/health_problem_list">
            <span>health problem list</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_record" title="https://contsys.org/concept/health_record">
            <span>health record</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_record_component"
            title="https://contsys.org/concept/health_record_component">
            <span>health record component</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_record_extract"
            title="https://contsys.org/concept/health_record_extract">
            <span>health record extract</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_state" title="https://contsys.org/concept/health_state">
            <span>health state</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_thread" title="https://contsys.org/concept/health_thread">
            <span>health thread</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare" title="https://contsys.org/concept/healthcare">healthcare</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_activities_bundle"
            title="https://contsys.org/concept/healthcare_activities_bundle">
            <span>healthcare activities bundle</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_activity_delay"
            title="https://contsys.org/concept/healthcare_activity_delay">
            <span>healthcare activity delay</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_activity_directory"
            title="https://contsys.org/concept/healthcare_activity_directory">
            <span>healthcare activity directory</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_activity_element"
            title="https://contsys.org/concept/healthcare_activity_element">
            <span>healthcare activity element</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_activity_management"
            title="https://contsys.org/concept/healthcare_activity_management">
            <span>healthcare activity management</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_activity_mandate"
            title="https://contsys.org/concept/healthcare_activity_mandate">
            <span>healthcare activity mandate</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_activity_period"
            title="https://contsys.org/concept/healthcare_activity_period">
            <span>healthcare activity period</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_activity_period_element"
            title="https://contsys.org/concept/healthcare_activity_period_element">
            <span>healthcare activity period element</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_actor" title="https://contsys.org/concept/healthcare_actor">
            <span>healthcare actor</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_administration"
            title="https://contsys.org/concept/healthcare_administration">
            <span>healthcare administration</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_assessment"
            title="https://contsys.org/concept/healthcare_assessment">
            <span>healthcare assessment</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_communication"
            title="https://contsys.org/concept/healthcare_communication">
            <span>healthcare communication</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_documenting"
            title="https://contsys.org/concept/healthcare_documenting">
            <span>healthcare documenting</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_evaluation"
            title="https://contsys.org/concept/healthcare_evaluation">
            <span>healthcare evaluation</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_funds" title="https://contsys.org/concept/healthcare_funds">
            <span>healthcare funds</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_goal" title="https://contsys.org/concept/healthcare_goal">
            <span>healthcare goal</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_information"
            title="https://contsys.org/concept/healthcare_information">
            <span>healthcare information</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_information_for_import"
            title="https://contsys.org/concept/healthcare_information_for_import">
            <span>healthcare information for import</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_investigation"
            title="https://contsys.org/concept/healthcare_investigation">
            <span>healthcare investigation</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_mandate" title="https://contsys.org/concept/healthcare_mandate">
            <span>healthcare mandate</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_matter" title="https://contsys.org/concept/healthcare_matter">
            <span>healthcare matter</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_needs_assessment"
            title="https://contsys.org/concept/healthcare_needs_assessment">
            <span>healthcare needs assessment</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_personnel"
            title="https://contsys.org/concept/healthcare_personnel">
            <span>healthcare personnel</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_planning" title="https://contsys.org/concept/healthcare_planning">
            <span>healthcare planning</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_process_evaluation"
            title="https://contsys.org/concept/healthcare_process_evaluation">
            <span>healthcare process evaluation</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_professional"
            title="https://contsys.org/concept/healthcare_professional">
            <span>healthcare professional</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_professional_entitlement"
            title="https://contsys.org/concept/healthcare_professional_entitlement">
            <span>healthcare professional entitlement</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_provider" title="https://contsys.org/concept/healthcare_provider">
            <span>healthcare provider</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_provider_activity"
            title="https://contsys.org/concept/healthcare_provider_activity">
            <span>healthcare provider activity</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_quality_management"
            title="https://contsys.org/concept/healthcare_quality_management">
            <span>healthcare quality management</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_resource" title="https://contsys.org/concept/healthcare_resource">
            <span>healthcare resource</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_resource_management"
            title="https://contsys.org/concept/healthcare_resource_management">
            <span>healthcare resource management</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_supporting_organization"
            title="https://contsys.org/concept/healthcare_supporting_organization">
            <span>healthcare supporting organization</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_third_party"
            title="https://contsys.org/concept/healthcare_third_party">
            <span>healthcare third party</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_third_party_activity"
            title="https://contsys.org/concept/healthcare_third_party_activity">
            <span>healthcare third party activity</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_treatment"
            title="https://contsys.org/concept/healthcare_treatment">
            <span>healthcare treatment</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_service_directory"
            title="https://contsys.org/concept/healthcare_service_directory">healthcare_service_directory</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_activity" title="https://contsys.org/concept/healthcare_activity">healthcareActivity</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_appointment"
            title="https://contsys.org/concept/healthcare_appointment">healthcareAppoinment</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_commitment"
            title="https://contsys.org/concept/healthcare_commitment">healthcareCommitment</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_information_request"
            title="https://contsys.org/concept/healthcare_information_request">healthcareInformationRequest</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_organization"
            title="https://contsys.org/concept/healthcare_organization">healthcareOrganization</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_process" title="https://contsys.org/concept/healthcare_process">healthcareProcess</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/healthcare_service" title="https://contsys.org/concept/healthcare_service">healthcareService</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/health_related_period"
            title="https://contsys.org/concept/health_related_period">healthRelatedPeriod</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/informed_consent" title="https://contsys.org/concept/informed_consent">
            <span>informed consent</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/initial_contact" title="https://contsys.org/concept/initial_contact">initialContact</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/input_health_state" title="https://contsys.org/concept/input_health_state">
            <span>input health state</span>
         </a>
      </li>
      <li>
         <a href="#location" title="http://purl.org/net/for-coc#location">
            <span>location</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/mandate_to_export_personal_information"
            title="https://contsys.org/concept/mandate_to_export_personal_information">
            <span>mandate to export personal information</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/mandated_period_of_care"
            title="https://contsys.org/concept/mandated_period_of_care">
            <span>mandated period of care</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/medical_device" title="https://contsys.org/concept/medical_device">medicalDevice</a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/MedicationRequest" title="http://hl7.org/fhir/MedicationRequest">
            <span>medication request</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/medicinal_product" title="https://contsys.org/concept/medicinal_product">
            <span>medicinal product</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/medium" title="https://contsys.org/concept/medium">
            <span>medium</span>
         </a>
      </li>
      <li>
         <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
            title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/multi-professional_care_plan"
            title="https://contsys.org/concept/multi-professional_care_plan">
            <span>multi professional care plan</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/needed_healthcare_activity"
            title="https://contsys.org/concept/needed_healthcare_activity">
            <span>needed healthcare activity</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/next_of_kin" title="https://contsys.org/concept/next_of_kin">
            <span>next of kin</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/non-ratified_healthcare_information"
            title="https://contsys.org/concept/non-ratified_healthcare_information">
            <span>non ratified healthcare information</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/observed_condition" title="https://contsys.org/concept/observed_condition">
            <span>observed condition</span>
         </a>
      </li>
      <li>
         <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Organization"
            title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Organization">organization</a>
      </li>
      <li>
         <a href="#d-ontology-781#organizationRole"
            title="http://purl.org/net/for-cocd-ontology-781#organizationRole">
            <span>organization role</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/other_carer" title="https://contsys.org/concept/other_carer">
            <span>other carer</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/output_health_state" title="https://contsys.org/concept/output_health_state">
            <span>output health state</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/party" title="https://contsys.org/concept/party">
            <span>party</span>
         </a>
      </li>
      <li>
         <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Natural-Person"
            title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Natural-Person">person</a>
      </li>
      <li>
         <a href="#d-ontology-781#personRole"
            title="http://purl.org/net/for-cocd-ontology-781#personRole">
            <span>person role</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/personal_health_record"
            title="https://contsys.org/concept/personal_health_record">
            <span>personal health record</span>
         </a>
      </li>
      <li>
         <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object"
            title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object">physicalObject</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/potential_health_condition"
            title="https://contsys.org/concept/potential_health_condition">
            <span>potential health condition</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/prescribed_self-care"
            title="https://contsys.org/concept/prescribed_self-care">
            <span>prescribed self care</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/prescribed_third_party_activity"
            title="https://contsys.org/concept/prescribed_third_party_activity">
            <span>prescribed third party activity</span>
         </a>
      </li>
      <li>
         <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Process"
            title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Process">process</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/product" title="https://contsys.org/concept/product">
            <span>product</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/professional_health_record"
            title="https://contsys.org/concept/professional_health_record">
            <span>professional health record</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/professionally_assessed_condition"
            title="https://contsys.org/concept/professionally_assessed_condition">
            <span>professionally assessed condition</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/prognostic_condition"
            title="https://contsys.org/concept/prognostic_condition">
            <span>prognostic condition</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/protocol" title="https://contsys.org/concept/protocol">
            <span>protocol</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/reason_for_demand_for_care"
            title="https://contsys.org/concept/reason_for_demand_for_care">
            <span>reason for demand for care</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/referral" title="https://contsys.org/concept/referral">referral</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/request" title="https://contsys.org/concept/request">request</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/resource" title="https://contsys.org/concept/resource">
            <span>resource</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/resource_delay" title="https://contsys.org/concept/resource_delay">
            <span>resource delay</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/resultant_condition" title="https://contsys.org/concept/resultant_condition">
            <span>resultant condition</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/risk_condition" title="https://contsys.org/concept/risk_condition">
            <span>risk condition</span>
         </a>
      </li>
      <li>
         <a href="#http://www.loa-cnr.it/ontologies/DnS#role" title="http://www.loa-cnr.it/ontologies/DnS#role">role</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/self-care_period" title="https://contsys.org/concept/self-care_period">
            <span>self care period</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/self-care_activity" title="https://contsys.org/concept/self-care_activity">selfCareActivity</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/service" title="https://contsys.org/concept/service">
            <span>service</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/sharable_data_repository"
            title="https://contsys.org/concept/sharable_data_repository">
            <span>sharable data repository</span>
         </a>
      </li>
      <li>
         <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State"
            title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State">state</a>
      </li>
      <li>
         <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Stative"
            title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Stative">stative</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/subject_of_care_desire"
            title="https://contsys.org/concept/subject_of_care_desire">
            <span>subject of care desire</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/subject_of_care_preference_delay"
            title="https://contsys.org/concept/subject_of_care_preference_delay">
            <span>subject of care preference delay</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/subject_of_care_proxy"
            title="https://contsys.org/concept/subject_of_care_proxy">
            <span>subject of care proxy</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/subject_of_care" title="https://contsys.org/concept/subject_of_care">subjectOfCare</a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/summarized_healthcare_information_repository"
            title="https://contsys.org/concept/summarized_healthcare_information_repository">
            <span>summarized healthcare information repository</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/target_condition" title="https://contsys.org/concept/target_condition">
            <span>target condition</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/uniprofessional_care_plan"
            title="https://contsys.org/concept/uniprofessional_care_plan">
            <span>uniprofessional care plan</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/working_diagnosis" title="https://contsys.org/concept/working_diagnosis">
            <span>working diagnosis</span>
         </a>
      </li>
   </ul>
   <div class="entity" id="https://contsys.org/concept/adverse_event_management">
      <h3>adverse event management<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/adverse_event_management</p>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity" title="https://contsys.org/concept/healthcare_activity">healthcareActivity</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/adverse_event">
      <h3>adverseEvent<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/adverse_event</p>
      <div class="comment">
         <span class="markdown">unintended event that has negative influence upon healthcare processes</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/appointment">
      <h3>appointment<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/appointment</p>
      <div class="comment">
         <span class="markdown">arrangement to meet someone at a particular time and place</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_appointment"
               title="https://contsys.org/concept/healthcare_appointment">healthcareAppoinment</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/authorization_by_law">
      <h3>authorization by law<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/authorization_by_law</p>
      <div class="comment">
         <span class="markdown">provision in legislation that in certain circumstances may overrule the need for informed consent</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/automated_healthcare">
      <h3>automatedHealthcare<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/automated_healthcare</p>
      <div class="comment">
         <span class="markdown">method of delivering healthcare initiated by a responsible healthcare actor and thereafter delivered automatically by an automatic medical device</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/automatic_medical_device">
      <h3>automatic medical device<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/automatic_medical_device</p>
      <div class="comment">
         <span class="markdown">medical device capable of performing automated healthcare activities</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/medical_device" title="https://contsys.org/concept/medical_device">medicalDevice</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/care_period_mandate">
      <h3>care period mandate<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/care_period_mandate</p>
      <div class="comment">
         <span class="markdown">healthcare mandate commissioning a mandated period of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_mandate" title="https://contsys.org/concept/healthcare_mandate">healthcare mandate</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/care_plan">
      <h3>care plan<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/care_plan</p>
      <div class="comment">
         <span class="markdown">dynamic, personalized plan including identified needed healthcare activities, health objectives and healthcare goals, relating to one or more specified health issues in a healthcare process</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/multi-professional_care_plan"
               title="https://contsys.org/concept/multi-professional_care_plan">multi professional care plan</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/uniprofessional_care_plan"
               title="https://contsys.org/concept/uniprofessional_care_plan">uniprofessional care plan</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/certificate_related_to_a_healthcare_matter">
      <h3>certificate related to a healthcare matter<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/certificate_related_to_a_healthcare_matter</p>
      <div class="comment">
         <span class="markdown">official document issued by a healthcare actor attesting healthcare matters relating to a subject of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/clinical_guideline">
      <h3>clinical guideline<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/clinical_guideline</p>
      <div class="comment">
         <span class="markdown">set of systematically developed statements to assist the decisions made by healthcare actors about healthcare activities to be performed with regard to specified health issues</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/protocol" title="https://contsys.org/concept/protocol">protocol</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/clinical_pathway">
      <h3>clinical pathway<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/clinical_pathway</p>
      <div class="comment">
         <span class="markdown">pathway for the healthcare activities informing the content of core care plans</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/clinical_process_episode">
      <h3>clinical process episode<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/clinical_process_episode</p>
      <div class="comment">
         <span class="markdown">health related period that includes all healthcare activity periods in one clinical process</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_related_period"
               title="https://contsys.org/concept/health_related_period">healthRelatedPeriod</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/clinical_process_interest">
      <h3>clinical process interest<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/clinical_process_interest</p>
      <div class="comment">
         <span class="markdown">health thread comprising all healthcare matters related to a specific clinical process</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_thread" title="https://contsys.org/concept/health_thread">health thread</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/clinical_process_outcome_evaluation">
      <h3>clinical process outcome evaluation<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/clinical_process_outcome_evaluation</p>
      <div class="comment">
         <span class="markdown">healthcare evaluation where the effects of a clinical process on a health state are assessed against the target condition and/or a health condition representing the input health state</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_evaluation"
               title="https://contsys.org/concept/healthcare_evaluation">healthcare evaluation</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/clinical_report">
      <h3>clinical report<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/clinical_report</p>
      <div class="comment">
         <span class="markdown">health record extract conveying specifically focused healthcare information in order to fulfil current information needs of the recipient</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_record_extract"
               title="https://contsys.org/concept/health_record_extract">health record extract</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/discharge_report" title="https://contsys.org/concept/discharge_report">discharge report</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/clinical_process">
      <h3>clinicalProcess<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/clinical_process</p>
      <div class="comment">
         <span class="markdown">healthcare process encompassing all healthcare provider activities and other prescribed healthcare activities that addresses identified or specified health issues</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_process" title="https://contsys.org/concept/healthcare_process">healthcareProcess</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/consent_competence">
      <h3>consent competence<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/consent_competence</p>
      <div class="comment">
         <span class="markdown">capability of the subject of care and/or the subject of care proxy to give informed consent or dissent</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/considered_condition">
      <h3>considered condition<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/considered_condition</p>
      <div class="comment">
         <span class="markdown">potential health condition considered by a healthcare actor on the basis of one or more observed conditions</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/potential_health_condition"
               title="https://contsys.org/concept/potential_health_condition">potential health condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/excluded_condition" title="https://contsys.org/concept/excluded_condition">excluded condition</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/working_diagnosis" title="https://contsys.org/concept/working_diagnosis">working diagnosis</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/contact">
      <h3>contact<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/contact</p>
      <div class="comment">
         <span class="markdown">interaction between a subject of care and one or more healthcare personnel</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/initial_contact" title="https://contsys.org/concept/initial_contact">initialContact</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/contact_period">
      <h3>contact period<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/contact_period</p>
      <div class="comment">
         <span class="markdown">healthcare activity period during which a contact occurs</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_period"
               title="https://contsys.org/concept/healthcare_activity_period">healthcare activity period</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/continuity_facilitator_mandate">
      <h3>continuity facilitator mandate<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/continuity_facilitator_mandate</p>
      <div class="comment">
         <span class="markdown">healthcare mandate assigning the right and obligation to monitor and coordinate the delivery of care described in those care period mandates related to healthcare matters linked by specific health threads</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_mandate" title="https://contsys.org/concept/healthcare_mandate">healthcare mandate</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/core_care_plan">
      <h3>core care plan<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/core_care_plan</p>
      <div class="comment">
         <span class="markdown">reusable content and structure for a potential care plan for a specified set of circumstances</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/data_repository">
      <h3>data repository<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/data_repository</p>
      <div class="comment">
         <span class="markdown">an identifiable data storage facility</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_record" title="https://contsys.org/concept/health_record">health record</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/health_record_component"
               title="https://contsys.org/concept/health_record_component">health record component</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/sharable_data_repository"
               title="https://contsys.org/concept/sharable_data_repository">sharable data repository</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/demand_for_initial_contact">
      <h3>demand for initial contact<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/demand_for_initial_contact</p>
      <div class="comment">
         <span class="markdown">first demand for care concerning one or more specific health issues to be assessed by a healthcare provider</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/demand_for_care" title="https://contsys.org/concept/demand_for_care">demandForCare</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/demand_mandate">
      <h3>demand mandate<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/demand_mandate</p>
      <div class="comment">
         <span class="markdown">healthcare mandate implying the right and obligation to demand healthcare activities</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_mandate" title="https://contsys.org/concept/healthcare_mandate">healthcare mandate</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/demand_for_care">
      <h3>demandForCare<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/demand_for_care</p>
      <div class="comment">
         <span class="markdown">demand for healthcare provider activities expressed by a healthcare actor</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/demand_for_initial_contact"
               title="https://contsys.org/concept/demand_for_initial_contact">demand for initial contact</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/referral" title="https://contsys.org/concept/referral">referral</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/request" title="https://contsys.org/concept/request">request</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/discharge_report">
      <h3>discharge report<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/discharge_report</p>
      <div class="comment">
         <span class="markdown">clinical report concerning a completed, mandated period of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/clinical_report" title="https://contsys.org/concept/clinical_report">clinical report</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/discharge_summary" title="https://contsys.org/concept/discharge_summary">discharge summary</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/discharge_summary">
      <h3>discharge summary<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/discharge_summary</p>
      <div class="comment">
         <span class="markdown">discharge report summarizing a mandated period of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/discharge_report" title="https://contsys.org/concept/discharge_report">discharge report</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/dissent">
      <h3>dissent<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/dissent</p>
      <div class="comment">
         <span class="markdown">refusal to permit specific healthcare activities to be performed</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/electronic_health_record_component">
      <h3>electronic health record component<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/electronic_health_record_component</p>
      <div class="comment">
         <span class="markdown">health record component which only includes information in electronic format</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_record_component"
               title="https://contsys.org/concept/health_record_component">health record component</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/electronic_health_record_extract">
      <h3>electronic health record extract<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/electronic_health_record_extract</p>
      <div class="comment">
         <span class="markdown">health record extract consisting solely of electronic record components</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_record_extract"
               title="https://contsys.org/concept/health_record_extract">health record extract</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/electronic_patient_summary"
               title="https://contsys.org/concept/electronic_patient_summary">electronic patient summary</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/electronic_patient_summary">
      <h3>electronic patient summary<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/electronic_patient_summary</p>
      <div class="comment">
         <span class="markdown">electronic health record extract containing essential healthcare information intended for specific uses</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/electronic_health_record_extract"
               title="https://contsys.org/concept/electronic_health_record_extract">electronic health record extract</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/episode_of_care">
      <h3>episode of care<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/episode_of_care</p>
      <div class="comment">
         <span class="markdown">health related period during which healthcare activities are performed to address one health issue as identified by one healthcare professional</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_related_period"
               title="https://contsys.org/concept/health_related_period">healthRelatedPeriod</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_approach" title="https://contsys.org/concept/health_approach">health approach</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_activity_period_element"
               title="https://contsys.org/concept/healthcare_activity_period_element">healthcare activity period element</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/episodes_of_care_bundle">
      <h3>episodes of care bundle<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/episodes_of_care_bundle</p>
      <div class="comment">
         <span class="markdown">group of episodes of care delineated by a health thread</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_related_period"
               title="https://contsys.org/concept/health_related_period">healthRelatedPeriod</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">
      <h3>event<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event</p>
      <div class="comment">
         <span class="markdown">something that happens at a given place and time</span>
      </div>
      <dl class="description">
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/adverse_event" title="https://contsys.org/concept/adverse_event">adverseEvent</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/appointment" title="https://contsys.org/concept/appointment">appointment</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/automated_healthcare"
               title="https://contsys.org/concept/automated_healthcare">automatedHealthcare</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/contact" title="https://contsys.org/concept/contact">contact</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/demand_for_care" title="https://contsys.org/concept/demand_for_care">demandForCare</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/dissent" title="https://contsys.org/concept/dissent">dissent</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/health_thread" title="https://contsys.org/concept/health_thread">health thread</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/health_related_period"
               title="https://contsys.org/concept/health_related_period">healthRelatedPeriod</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare" title="https://contsys.org/concept/healthcare">healthcare</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_activity_element"
               title="https://contsys.org/concept/healthcare_activity_element">healthcare activity element</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_administration"
               title="https://contsys.org/concept/healthcare_administration">healthcare administration</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_activity" title="https://contsys.org/concept/healthcare_activity">healthcareActivity</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_commitment"
               title="https://contsys.org/concept/healthcare_commitment">healthcareCommitment</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/service" title="https://contsys.org/concept/service">service</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/excluded_condition">
      <h3>excluded condition<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/excluded_condition</p>
      <div class="comment">
         <span class="markdown">considered condition that one or more healthcare professionals have determined not to be consistent with the known observed conditions</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/considered_condition"
               title="https://contsys.org/concept/considered_condition">considered condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_approach">
      <h3>health approach<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_approach</p>
      <div class="comment">
         <span class="markdown">episode of care during which the healthcare activities performed address one specific healthcare goal</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/episode_of_care" title="https://contsys.org/concept/episode_of_care">episode of care</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_concern">
      <h3>health concern<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_concern</p>
      <div class="comment">
         <span class="markdown">health record extract that includes all health record components associated with a health thread for a specific concern</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_record_extract"
               title="https://contsys.org/concept/health_record_extract">health record extract</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_condition">
      <h3>health condition<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_condition</p>
      <div class="comment">
         <span class="markdown">observed or potential observable aspects of the health state at a given time</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_issue" title="https://contsys.org/concept/health_issue">health issue</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_problem" title="https://contsys.org/concept/health_problem">health problem</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/observed_condition" title="https://contsys.org/concept/observed_condition">observed condition</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/potential_health_condition"
               title="https://contsys.org/concept/potential_health_condition">potential health condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_condition_delay">
      <h3>health condition delay<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_condition_delay</p>
      <div class="comment">
         <span class="markdown">healthcare activity delay caused by a health condition</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_delay"
               title="https://contsys.org/concept/healthcare_activity_delay">healthcare activity delay</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_condition_evolution">
      <h3>health condition evolution<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_condition_evolution</p>
      <div class="comment">
         <span class="markdown">health thread showing the evolution of health conditions during a healthcare process, starting with the health condition that represents the input health state</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_thread" title="https://contsys.org/concept/health_thread">health thread</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_condition_period">
      <h3>health condition period<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_condition_period</p>
      <div class="comment">
         <span class="markdown">health related period during which a health condition has been observed</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_related_period"
               title="https://contsys.org/concept/health_related_period">healthRelatedPeriod</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_issue">
      <h3>health issue<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_issue</p>
      <div class="comment">
         <span class="markdown">representation of an issue related to the health of a subject of care as identified by one or more healthcare actors</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_matter" title="https://contsys.org/concept/healthcare_matter">healthcare matter</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_condition" title="https://contsys.org/concept/health_condition">health condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_need">
      <h3>health need<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_need</p>
      <div class="comment">
         <span class="markdown">deficit in the current health state compared to aspects of a desired future health state</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State">state</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_objective">
      <h3>health objective<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_objective</p>
      <div class="comment">
         <span class="markdown">desired ultimate achievement of a healthcare process addressing health needs</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_problem">
      <h3>health problem<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_problem</p>
      <div class="comment">
         <span class="markdown">health condition considered by a healthcare actor to be a problem</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_condition" title="https://contsys.org/concept/health_condition">health condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_problem_list">
      <h3>health problem list<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_problem_list</p>
      <div class="comment">
         <span class="markdown">health thread linking a set of health problems</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_thread" title="https://contsys.org/concept/health_thread">health thread</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_record">
      <h3>health record<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_record</p>
      <div class="comment">
         <span class="markdown">data repository regarding the health and healthcare of a subject of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/data_repository" title="https://contsys.org/concept/data_repository">data repository</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/personal_health_record"
               title="https://contsys.org/concept/personal_health_record">personal health record</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/professional_health_record"
               title="https://contsys.org/concept/professional_health_record">professional health record</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_record_component">
      <h3>health record component<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_record_component</p>
      <div class="comment">
         <span class="markdown">part of a health record that is identifiable for the purposes of referencing and revision</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/data_repository" title="https://contsys.org/concept/data_repository">data repository</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/electronic_health_record_component"
               title="https://contsys.org/concept/electronic_health_record_component">electronic health record component</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_record_extract">
      <h3>health record extract<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_record_extract</p>
      <div class="comment">
         <span class="markdown">part or all of a health record extracted for the purpose of communication</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/clinical_report" title="https://contsys.org/concept/clinical_report">clinical report</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/electronic_health_record_extract"
               title="https://contsys.org/concept/electronic_health_record_extract">electronic health record extract</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/health_concern" title="https://contsys.org/concept/health_concern">health concern</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_state">
      <h3>health state<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_state</p>
      <div class="comment">
         <span class="markdown">physical and mental functions, body structure, personal factors, activity, participation and environmental aspects as the composite health of a subject of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State">state</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/input_health_state" title="https://contsys.org/concept/input_health_state">input health state</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/output_health_state" title="https://contsys.org/concept/output_health_state">output health state</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_thread">
      <h3>health thread<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_thread</p>
      <div class="comment">
         <span class="markdown">defined association between healthcare matters as determined by one or more healthcare actors</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/clinical_process_interest"
               title="https://contsys.org/concept/clinical_process_interest">clinical process interest</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/health_condition_evolution"
               title="https://contsys.org/concept/health_condition_evolution">health condition evolution</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/health_problem_list" title="https://contsys.org/concept/health_problem_list">health problem list</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare">
      <h3>healthcare<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare</p>
      <div class="comment">
         <span class="markdown">care activities, services, management or supplies related to the health of an individual</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_activities_bundle">
      <h3>healthcare activities bundle<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_activities_bundle</p>
      <div class="comment">
         <span class="markdown">set of healthcare activities</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity" title="https://contsys.org/concept/healthcare_activity">healthcareActivity</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/needed_healthcare_activity"
               title="https://contsys.org/concept/needed_healthcare_activity">needed healthcare activity</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_activity_delay">
      <h3>healthcare activity delay<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_activity_delay</p>
      <div class="comment">
         <span class="markdown">health related period during which a healthcare activity is planned but not started</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_related_period"
               title="https://contsys.org/concept/health_related_period">healthRelatedPeriod</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_condition_delay"
               title="https://contsys.org/concept/health_condition_delay">health condition delay</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/resource_delay" title="https://contsys.org/concept/resource_delay">resource delay</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/subject_of_care_preference_delay"
               title="https://contsys.org/concept/subject_of_care_preference_delay">subject of care preference delay</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_activity_directory">
      <h3>healthcare activity directory<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_activity_directory</p>
      <div class="comment">
         <span class="markdown">directory of the healthcare activities offered by a healthcare provider</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_activity_element">
      <h3>healthcare activity element<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_activity_element</p>
      <div class="comment">
         <span class="markdown">element of healthcare activity that addresses one type of purpose</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_management"
               title="https://contsys.org/concept/healthcare_activity_management">healthcare activity management</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_assessment"
               title="https://contsys.org/concept/healthcare_assessment">healthcare assessment</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_communication"
               title="https://contsys.org/concept/healthcare_communication">healthcare communication</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_documenting"
               title="https://contsys.org/concept/healthcare_documenting">healthcare documenting</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_evaluation"
               title="https://contsys.org/concept/healthcare_evaluation">healthcare evaluation</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_investigation"
               title="https://contsys.org/concept/healthcare_investigation">healthcare investigation</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_quality_management"
               title="https://contsys.org/concept/healthcare_quality_management">healthcare quality management</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_resource_management"
               title="https://contsys.org/concept/healthcare_resource_management">healthcare resource management</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_treatment"
               title="https://contsys.org/concept/healthcare_treatment">healthcare treatment</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_activity_management">
      <h3>healthcare activity management<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_activity_management</p>
      <div class="comment">
         <span class="markdown">healthcare activity element during which the status of healthcare activities in a care plan are changed</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_element"
               title="https://contsys.org/concept/healthcare_activity_element">healthcare activity element</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_activity_mandate">
      <h3>healthcare activity mandate<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_activity_mandate</p>
      <div class="comment">
         <span class="markdown">healthcare mandate assigning the right and obligation to perform specific healthcare activities</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_mandate" title="https://contsys.org/concept/healthcare_mandate">healthcare mandate</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_activity_period">
      <h3>healthcare activity period<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_activity_period</p>
      <div class="comment">
         <span class="markdown">time interval during which healthcare activities are performed for a subject of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_related_period"
               title="https://contsys.org/concept/health_related_period">healthRelatedPeriod</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/contact_period" title="https://contsys.org/concept/contact_period">contact period</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/self-care_period" title="https://contsys.org/concept/self-care_period">self care period</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_activity_period_element">
      <h3>healthcare activity period element<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_activity_period_element</p>
      <div class="comment">
         <span class="markdown">part of a healthcare activity period during which one health issue is specifically addressed</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/episode_of_care" title="https://contsys.org/concept/episode_of_care">episode of care</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_actor">
      <h3>healthcare actor<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_actor</p>
      <div class="comment">
         <span class="markdown">organization or person participating in healthcare</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://www.loa-cnr.it/ontologies/DnS#role" title="http://www.loa-cnr.it/ontologies/DnS#role">role</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_personnel"
               title="https://contsys.org/concept/healthcare_personnel">healthcare personnel</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_provider" title="https://contsys.org/concept/healthcare_provider">healthcare provider</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_third_party"
               title="https://contsys.org/concept/healthcare_third_party">healthcare third party</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/subject_of_care" title="https://contsys.org/concept/subject_of_care">subjectOfCare</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_administration">
      <h3>healthcare administration<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_administration</p>
      <div class="comment">
         <span class="markdown">administrative activities related to healthcare processes</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_assessment">
      <h3>healthcare assessment<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_assessment</p>
      <div class="comment">
         <span class="markdown">healthcare activity element where an opinion related to health conditions and/or healthcare activities is formed</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_element"
               title="https://contsys.org/concept/healthcare_activity_element">healthcare activity element</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_needs_assessment"
               title="https://contsys.org/concept/healthcare_needs_assessment">healthcare needs assessment</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_communication">
      <h3>healthcare communication<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_communication</p>
      <div class="comment">
         <span class="markdown">healthcare activity element where at least two healthcare actors communicate</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_element"
               title="https://contsys.org/concept/healthcare_activity_element">healthcare activity element</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_documenting">
      <h3>healthcare documenting<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_documenting</p>
      <div class="comment">
         <span class="markdown">healthcare activity element where health records are created or maintained</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_element"
               title="https://contsys.org/concept/healthcare_activity_element">healthcare activity element</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_evaluation">
      <h3>healthcare evaluation<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_evaluation</p>
      <div class="comment">
         <span class="markdown">healthcare activity element where aspects of at least one other healthcare activity element is evaluated</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_element"
               title="https://contsys.org/concept/healthcare_activity_element">healthcare activity element</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/clinical_process_outcome_evaluation"
               title="https://contsys.org/concept/clinical_process_outcome_evaluation">clinical process outcome evaluation</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_process_evaluation"
               title="https://contsys.org/concept/healthcare_process_evaluation">healthcare process evaluation</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_funds">
      <h3>healthcare funds<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_funds</p>
      <div class="comment">
         <span class="markdown">resource provided for funding healthcare delivery</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/resource" title="https://contsys.org/concept/resource">resource</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_goal">
      <h3>healthcare goal<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_goal</p>
      <div class="comment">
         <span class="markdown">desired achievement of one or more healthcare activities, considered as an intermediate operational step to reach a specific health objective</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_information">
      <h3>healthcare information<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_information</p>
      <div class="comment">
         <span class="markdown">information about a person, relevant to his or her healthcare</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_information_for_import"
               title="https://contsys.org/concept/healthcare_information_for_import">healthcare information for import</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/non-ratified_healthcare_information"
               title="https://contsys.org/concept/non-ratified_healthcare_information">non ratified healthcare information</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_information_for_import">
      <h3>healthcare information for import<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_information_for_import</p>
      <div class="comment">
         <span class="markdown">healthcare information that is a candidate for import into a professional health record after a healthcare professional has confirmed its clinical relevance to that professional health record</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_information"
               title="https://contsys.org/concept/healthcare_information">healthcare information</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_investigation">
      <h3>healthcare investigation<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_investigation</p>
      <div class="comment">
         <span class="markdown">healthcare activity element with the intention to clarify one or more health conditions of a subject of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_element"
               title="https://contsys.org/concept/healthcare_activity_element">healthcare activity element</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_mandate">
      <h3>healthcare mandate<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_mandate</p>
      <div class="comment">
         <span class="markdown">mandate (commission) based on a commitment and either an informed consent or an authorization by law, defining the rights and obligations of one healthcare actor with regard to his involvement in healthcare processes performed for a specific subject of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/care_period_mandate" title="https://contsys.org/concept/care_period_mandate">care period mandate</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/continuity_facilitator_mandate"
               title="https://contsys.org/concept/continuity_facilitator_mandate">continuity facilitator mandate</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/demand_mandate" title="https://contsys.org/concept/demand_mandate">demand mandate</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_activity_mandate"
               title="https://contsys.org/concept/healthcare_activity_mandate">healthcare activity mandate</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/mandate_to_export_personal_information"
               title="https://contsys.org/concept/mandate_to_export_personal_information">mandate to export personal information</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_matter">
      <h3>healthcare matter<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_matter</p>
      <div class="comment">
         <span class="markdown">representation of a matter related to the health of a subject of care and/or the provision of healthcare to that subject of care, as identified by one or more healthcare actors</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State">state</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_issue" title="https://contsys.org/concept/health_issue">health issue</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_needs_assessment">
      <h3>healthcare needs assessment<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_needs_assessment</p>
      <div class="comment">
         <span class="markdown">healthcare assessment during which a healthcare professional considers a subject of care’s health need and determines the needed healthcare activities</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_assessment"
               title="https://contsys.org/concept/healthcare_assessment">healthcare assessment</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_personnel">
      <h3>healthcare personnel<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_personnel</p>
      <div class="comment">
         <span class="markdown">individual healthcare actor having a person role in a healthcare organization</span>
      </div>
      <dl>
         <dt>Example</dt>
         <dd>
            <pre>EXAMPLES       GP, medical consultant, therapist, dentist, nurse, social worker, radiographer, nurse’s assistant, children’s nurse, nursing officer, head of department, social worker, medical consultant, etc.</pre>
         </dd>
      </dl>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_actor" title="https://contsys.org/concept/healthcare_actor">healthcare actor</a>
            <sup class="type-c" title="class">c</sup>, <a href="#d-ontology-781#personRole"
               title="http://purl.org/net/for-cocd-ontology-781#personRole">person role</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_professional"
               title="https://contsys.org/concept/healthcare_professional">healthcare professional</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_planning">
      <h3>healthcare planning<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_planning</p>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_process_evaluation">
      <h3>healthcare process evaluation<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_process_evaluation</p>
      <div class="comment">
         <span class="markdown">healthcare evaluation where healthcare processes are systematically assessed against requirements</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_evaluation"
               title="https://contsys.org/concept/healthcare_evaluation">healthcare evaluation</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_professional">
      <h3>healthcare professional<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_professional</p>
      <div class="comment">
         <span class="markdown">healthcare personnel having a healthcare professional entitlement recognized in a given jurisdiction</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_personnel"
               title="https://contsys.org/concept/healthcare_personnel">healthcare personnel</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_provider" title="https://contsys.org/concept/healthcare_provider">healthcare provider</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_professional_entitlement">
      <h3>healthcare professional entitlement<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_professional_entitlement</p>
      <div class="comment">
         <span class="markdown">registered authorization given to a person in order to allow the person to have or perform specific roles in healthcare</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_provider">
      <h3>healthcare provider<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_provider</p>
      <div class="comment">
         <span class="markdown">healthcare actor that is able to be assigned one or more care period mandates</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_actor" title="https://contsys.org/concept/healthcare_actor">healthcare actor</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_professional"
               title="https://contsys.org/concept/healthcare_professional">healthcare professional</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_organization"
               title="https://contsys.org/concept/healthcare_organization">healthcareOrganization</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_provider_activity">
      <h3>healthcare provider activity<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_provider_activity</p>
      <div class="comment">
         <span class="markdown">healthcare activity performed by a healthcare provider</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity" title="https://contsys.org/concept/healthcare_activity">healthcareActivity</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_quality_management">
      <h3>healthcare quality management<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_quality_management</p>
      <div class="comment">
         <span class="markdown">coordinated activities to direct and control a healthcare organization with regard to quality</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_element"
               title="https://contsys.org/concept/healthcare_activity_element">healthcare activity element</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_resource">
      <h3>healthcare resource<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_resource</p>
      <div class="comment">
         <span class="markdown">resource needed to perform healthcare activities</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/resource" title="https://contsys.org/concept/resource">resource</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_resource_management">
      <h3>healthcare resource management<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_resource_management</p>
      <div class="comment">
         <span class="markdown">activities to direct and control the supply and use of the healthcare resources required to perform healthcare activities</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_element"
               title="https://contsys.org/concept/healthcare_activity_element">healthcare activity element</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_supporting_organization">
      <h3>healthcare supporting organization<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_supporting_organization</p>
      <div class="comment">
         <span class="markdown">healthcare third party having organizational role</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_third_party"
               title="https://contsys.org/concept/healthcare_third_party">healthcare third party</a>
            <sup class="type-c" title="class">c</sup>, <a href="#d-ontology-781#organizationRole"
               title="http://purl.org/net/for-cocd-ontology-781#organizationRole">organization role</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_third_party">
      <h3>healthcare third party<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_third_party</p>
      <div class="comment">
         <span class="markdown">healthcare actor other than a healthcare provider or the subject of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_actor" title="https://contsys.org/concept/healthcare_actor">healthcare actor</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_supporting_organization"
               title="https://contsys.org/concept/healthcare_supporting_organization">healthcare supporting organization</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/other_carer" title="https://contsys.org/concept/other_carer">other carer</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/subject_of_care_proxy"
               title="https://contsys.org/concept/subject_of_care_proxy">subject of care proxy</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_third_party_activity">
      <h3>healthcare third party activity<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_third_party_activity</p>
      <div class="comment">
         <span class="markdown">healthcare activity performed by a healthcare third party</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity" title="https://contsys.org/concept/healthcare_activity">healthcareActivity</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/prescribed_third_party_activity"
               title="https://contsys.org/concept/prescribed_third_party_activity">prescribed third party activity</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_treatment">
      <h3>healthcare treatment<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_treatment</p>
      <div class="comment">
         <span class="markdown">healthcare activity element intended to directly improve or maintain a health state</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_element"
               title="https://contsys.org/concept/healthcare_activity_element">healthcare activity element</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_service_directory">
      <h3>healthcare_service_directory<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_service_directory</p>
      <div class="comment">
         <span class="markdown">directory of the types of healthcare services offered by one or more healthcare providers</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_activity">
      <h3>healthcareActivity<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_activity</p>
      <div class="comment">
         <span class="markdown">activity intended directly or indirectly to improve or maintain a health state</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/adverse_event_management"
               title="https://contsys.org/concept/adverse_event_management">adverse event management</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_activities_bundle"
               title="https://contsys.org/concept/healthcare_activities_bundle">healthcare activities bundle</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_provider_activity"
               title="https://contsys.org/concept/healthcare_provider_activity">healthcare provider activity</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_third_party_activity"
               title="https://contsys.org/concept/healthcare_third_party_activity">healthcare third party activity</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/self-care_activity" title="https://contsys.org/concept/self-care_activity">selfCareActivity</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_appointment">
      <h3>healthcareAppoinment<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_appointment</p>
      <div class="comment">
         <span class="markdown">appointment for a contact</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/appointment" title="https://contsys.org/concept/appointment">appointment</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_commitment">
      <h3>healthcareCommitment<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_commitment</p>
      <div class="comment">
         <span class="markdown">acceptance of a healthcare mandate by the healthcare actor to whom it is assigned</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_information_request">
      <h3>healthcareInformationRequest<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_information_request</p>
      <div class="comment">
         <span class="markdown">request sent out by a healthcare actor to another healthcare actor for specific healthcare information needed for the provision of healthcare to a subject of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/request" title="https://contsys.org/concept/request">request</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_organization">
      <h3>healthcareOrganization<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_organization</p>
      <div class="comment">
         <span class="markdown">healthcare provider having an organization role</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_provider" title="https://contsys.org/concept/healthcare_provider">healthcare provider</a>
            <sup class="type-c" title="class">c</sup>, <a href="#d-ontology-781#organizationRole"
               title="http://purl.org/net/for-cocd-ontology-781#organizationRole">organization role</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_process">
      <h3>healthcareProcess<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_process</p>
      <div class="comment">
         <span class="markdown">set of interrelated or interacting healthcare activities which transforms inputs into outputs</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Process"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Process">process</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/clinical_process" title="https://contsys.org/concept/clinical_process">clinicalProcess</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/healthcare_service">
      <h3>healthcareService<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/healthcare_service</p>
      <div class="comment">
         <span class="markdown">service that is the result of a healthcare process. Ex. Diagnostic investigation and result report.</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/service" title="https://contsys.org/concept/service">service</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/health_related_period">
      <h3>healthRelatedPeriod<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/health_related_period</p>
      <div class="comment">
         <span class="markdown">time interval related to the health of a subject of care and/or the provision of healthcare for that subject of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/clinical_process_episode"
               title="https://contsys.org/concept/clinical_process_episode">clinical process episode</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/episode_of_care" title="https://contsys.org/concept/episode_of_care">episode of care</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/episodes_of_care_bundle"
               title="https://contsys.org/concept/episodes_of_care_bundle">episodes of care bundle</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/health_condition_period"
               title="https://contsys.org/concept/health_condition_period">health condition period</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_activity_delay"
               title="https://contsys.org/concept/healthcare_activity_delay">healthcare activity delay</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_activity_period"
               title="https://contsys.org/concept/healthcare_activity_period">healthcare activity period</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/mandated_period_of_care"
               title="https://contsys.org/concept/mandated_period_of_care">mandated period of care</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/informed_consent">
      <h3>informed consent<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/informed_consent</p>
      <div class="comment">
         <span class="markdown">permission to perform healthcare activities, voluntarily given by a subject of care having consent competence, or by a subject of care proxy, after having been informed about the purpose and the possible results of the healthcare activities</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/initial_contact">
      <h3>initialContact<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/initial_contact</p>
      <div class="comment">
         <span class="markdown">contact during which a clinical process is initiated</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/contact" title="https://contsys.org/concept/contact">contact</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/input_health_state">
      <h3>input health state<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/input_health_state</p>
      <div class="comment">
         <span class="markdown">health state at the initiation of healthcare process</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_state" title="https://contsys.org/concept/health_state">health state</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="location">
      <h3>location<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://purl.org/net/for-coc#location</p>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object">physicalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/mandate_to_export_personal_information">
      <h3>mandate to export personal information<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/mandate_to_export_personal_information</p>
      <div class="comment">
         <span class="markdown">healthcare mandate implying the right to communicate health record extracts</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_mandate" title="https://contsys.org/concept/healthcare_mandate">healthcare mandate</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/mandated_period_of_care">
      <h3>mandated period of care<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/mandated_period_of_care</p>
      <div class="comment">
         <span class="markdown">set of healthcare activity periods where a healthcare provider is mandated to perform the healthcare activities required to address specific health needs. Ex. A hospital stay, a series of radiotherapy sessions at an outpatient clinic.</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_related_period"
               title="https://contsys.org/concept/health_related_period">healthRelatedPeriod</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/medical_device">
      <h3>medicalDevice<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/medical_device</p>
      <div class="comment">
         <span class="markdown">any instrument, apparatus, implement, machine, appliance, implant, in vitro reagent or calibrator, software, material or other similar or related article, intended by the manufacturer to be used, alone or in combination, for human beings for one or more of the specific purpose(s) of</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object">physicalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/automatic_medical_device"
               title="https://contsys.org/concept/automatic_medical_device">automatic medical device</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="http://hl7.org/fhir/MedicationRequest">
      <h3>medication request<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/MedicationRequest</p>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/request" title="https://contsys.org/concept/request">request</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/medicinal_product">
      <h3>medicinal product<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/medicinal_product</p>
      <div class="comment">
         <span class="markdown">any substance or combination of substances that can be administered to human beings for treating or preventing disease, with the view to making a medical diagnosis or to restore, correct, or modify physiological functions</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/product" title="https://contsys.org/concept/product">product</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/medium">
      <h3>medium<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/medium</p>
      <div class="comment">
         <span class="markdown">medium: material on which data is stored (e.g., a magnetic disk).</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object">physicalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">
      <h3>mentalObject<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object</p>
      <div class="comment">
         <span class="markdown">AKA "internal description". Mental objects are dependent on an intentional agent</span>
      </div>
      <dl class="description">
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/authorization_by_law"
               title="https://contsys.org/concept/authorization_by_law">authorization by law</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/care_plan" title="https://contsys.org/concept/care_plan">care plan</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/certificate_related_to_a_healthcare_matter"
               title="https://contsys.org/concept/certificate_related_to_a_healthcare_matter">certificate related to a healthcare matter</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/clinical_guideline" title="https://contsys.org/concept/clinical_guideline">clinical guideline</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/clinical_pathway" title="https://contsys.org/concept/clinical_pathway">clinical pathway</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/consent_competence" title="https://contsys.org/concept/consent_competence">consent competence</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/core_care_plan" title="https://contsys.org/concept/core_care_plan">core care plan</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/data_repository" title="https://contsys.org/concept/data_repository">data repository</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/health_objective" title="https://contsys.org/concept/health_objective">health objective</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/health_record_extract"
               title="https://contsys.org/concept/health_record_extract">health record extract</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_activity_directory"
               title="https://contsys.org/concept/healthcare_activity_directory">healthcare activity directory</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_goal" title="https://contsys.org/concept/healthcare_goal">healthcare goal</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_information"
               title="https://contsys.org/concept/healthcare_information">healthcare information</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_mandate" title="https://contsys.org/concept/healthcare_mandate">healthcare mandate</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_planning" title="https://contsys.org/concept/healthcare_planning">healthcare planning</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_professional_entitlement"
               title="https://contsys.org/concept/healthcare_professional_entitlement">healthcare professional entitlement</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_service_directory"
               title="https://contsys.org/concept/healthcare_service_directory">healthcare_service_directory</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/informed_consent" title="https://contsys.org/concept/informed_consent">informed consent</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/reason_for_demand_for_care"
               title="https://contsys.org/concept/reason_for_demand_for_care">reason for demand for care</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/resource" title="https://contsys.org/concept/resource">resource</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/multi-professional_care_plan">
      <h3>multi professional care plan<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/multi-professional_care_plan</p>
      <div class="comment">
         <span class="markdown">care plan encompassing healthcare provider activities performed by healthcare professionals having different healthcare professional entitlements</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/care_plan" title="https://contsys.org/concept/care_plan">care plan</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/needed_healthcare_activity">
      <h3>needed healthcare activity<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/needed_healthcare_activity</p>
      <div class="comment">
         <span class="markdown">healthcare activities bundle which includes those healthcare activities assessed as needed to address specified health need</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activities_bundle"
               title="https://contsys.org/concept/healthcare_activities_bundle">healthcare activities bundle</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/next_of_kin">
      <h3>next of kin<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/next_of_kin</p>
      <div class="comment">
         <span class="markdown">person role being either the closest living relative of the subject of care or identified as the one he has a close relationship with</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#d-ontology-781#personRole"
               title="http://purl.org/net/for-cocd-ontology-781#personRole">person role</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/non-ratified_healthcare_information">
      <h3>non ratified healthcare information<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/non-ratified_healthcare_information</p>
      <div class="comment">
         <span class="markdown">healthcare information the relevance of which has not been assessed and explicitly stated as valid by a healthcare professional</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_information"
               title="https://contsys.org/concept/healthcare_information">healthcare information</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/observed_condition">
      <h3>observed condition<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/observed_condition</p>
      <div class="comment">
         <span class="markdown">health condition observed by a healthcare actor</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_condition" title="https://contsys.org/concept/health_condition">health condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/professionally_assessed_condition"
               title="https://contsys.org/concept/professionally_assessed_condition">professionally assessed condition</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/resultant_condition" title="https://contsys.org/concept/resultant_condition">resultant condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Organization">
      <h3>organization<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Organization</p>
      <div class="comment">
         <span class="markdown">unique framework of authority within which a person (3.3.4) or persons act, or are designated to act towards some purpose</span>
      </div>
   </div>
   <div class="entity" id="d-ontology-781#organizationRole">
      <h3>organization role<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://purl.org/net/for-cocd-ontology-781#organizationRole</p>
      <div class="comment">
         <span class="markdown">role undertaken by an organization</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://www.loa-cnr.it/ontologies/DnS#role" title="http://www.loa-cnr.it/ontologies/DnS#role">role</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_supporting_organization"
               title="https://contsys.org/concept/healthcare_supporting_organization">healthcare supporting organization</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_organization"
               title="https://contsys.org/concept/healthcare_organization">healthcareOrganization</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>is disjoint with</dt>
         <dd>
            <a href="#d-ontology-781#personRole"
               title="http://purl.org/net/for-cocd-ontology-781#personRole">person role</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/other_carer">
      <h3>other carer<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/other_carer</p>
      <div class="comment">
         <span class="markdown">healthcare third party having person role</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_third_party"
               title="https://contsys.org/concept/healthcare_third_party">healthcare third party</a>
            <sup class="type-c" title="class">c</sup>, <a href="#d-ontology-781#personRole"
               title="http://purl.org/net/for-cocd-ontology-781#personRole">person role</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/output_health_state">
      <h3>output health state<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/output_health_state</p>
      <div class="comment">
         <span class="markdown">health state when a healthcare process ends</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_state" title="https://contsys.org/concept/health_state">health state</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/party">
      <h3>party<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/party</p>
      <div class="comment">
         <span class="markdown">person or group performing a role in relation to the business of a specific community or domain</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://www.loa-cnr.it/ontologies/DnS#role" title="http://www.loa-cnr.it/ontologies/DnS#role">role</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Natural-Person">
      <h3>person<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Natural-Person</p>
      <div class="comment">
         <span class="markdown">human being regarded as an individual</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object">physicalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="d-ontology-781#personRole">
      <h3>person role<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://purl.org/net/for-cocd-ontology-781#personRole</p>
      <div class="comment">
         <span class="markdown">role of a person</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://www.loa-cnr.it/ontologies/DnS#role" title="http://www.loa-cnr.it/ontologies/DnS#role">role</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_personnel"
               title="https://contsys.org/concept/healthcare_personnel">healthcare personnel</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/next_of_kin" title="https://contsys.org/concept/next_of_kin">next of kin</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/other_carer" title="https://contsys.org/concept/other_carer">other carer</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/subject_of_care_proxy"
               title="https://contsys.org/concept/subject_of_care_proxy">subject of care proxy</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/subject_of_care" title="https://contsys.org/concept/subject_of_care">subjectOfCare</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>is disjoint with</dt>
         <dd>
            <a href="#d-ontology-781#organizationRole"
               title="http://purl.org/net/for-cocd-ontology-781#organizationRole">organization role</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/personal_health_record">
      <h3>personal health record<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/personal_health_record</p>
      <div class="comment">
         <span class="markdown">health record held and maintained by the subject of care or a subject of care proxy</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_record" title="https://contsys.org/concept/health_record">health record</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object">
      <h3>physicalObject<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object</p>
      <dl class="description">
         <dt>has sub-classes</dt>
         <dd>
            <a href="#location" title="http://purl.org/net/for-coc#location">location</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/medical_device" title="https://contsys.org/concept/medical_device">medicalDevice</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/medium" title="https://contsys.org/concept/medium">medium</a>
            <sup class="type-c" title="class">c</sup>, <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Natural-Person"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Natural-Person">person</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/product" title="https://contsys.org/concept/product">product</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/potential_health_condition">
      <h3>potential health condition<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/potential_health_condition</p>
      <div class="comment">
         <span class="markdown">possible future or current health condition described by a healthcare actor</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_condition" title="https://contsys.org/concept/health_condition">health condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/considered_condition"
               title="https://contsys.org/concept/considered_condition">considered condition</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/prognostic_condition"
               title="https://contsys.org/concept/prognostic_condition">prognostic condition</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/risk_condition" title="https://contsys.org/concept/risk_condition">risk condition</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/target_condition" title="https://contsys.org/concept/target_condition">target condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/prescribed_self-care">
      <h3>prescribed self care<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/prescribed_self-care</p>
      <div class="comment">
         <span class="markdown">self-care activity prescribed by a healthcare professional</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/self-care_activity" title="https://contsys.org/concept/self-care_activity">selfCareActivity</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/prescribed_third_party_activity">
      <h3>prescribed third party activity<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/prescribed_third_party_activity</p>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_third_party_activity"
               title="https://contsys.org/concept/healthcare_third_party_activity">healthcare third party activity</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Process">
      <h3>process<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Process</p>
      <div class="comment">
         <span class="markdown">set of interrelated or interacting activities that use inputs to deliver an intended result</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Stative"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Stative">stative</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_process" title="https://contsys.org/concept/healthcare_process">healthcareProcess</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/product">
      <h3>product<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/product</p>
      <div class="comment">
         <span class="markdown">output of an organization that can be produced without any transaction taking place between the organization and the customer</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Physical-Object">physicalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/medicinal_product" title="https://contsys.org/concept/medicinal_product">medicinal product</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/professional_health_record">
      <h3>professional health record<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/professional_health_record</p>
      <div class="comment">
         <span class="markdown">health record held under the responsibility of one healthcare provider and maintained by one or several healthcare professionals</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_record" title="https://contsys.org/concept/health_record">health record</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/professionally_assessed_condition">
      <h3>professionally assessed condition<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/professionally_assessed_condition</p>
      <div class="comment">
         <span class="markdown">observed condition assessed by a healthcare professional concerning the genesis, the course, the severity or the impact of the health state</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/observed_condition" title="https://contsys.org/concept/observed_condition">observed condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/working_diagnosis" title="https://contsys.org/concept/working_diagnosis">working diagnosis</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/prognostic_condition">
      <h3>prognostic condition<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/prognostic_condition</p>
      <div class="comment">
         <span class="markdown">possible future or current health condition described by a healthcare actor</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/potential_health_condition"
               title="https://contsys.org/concept/potential_health_condition">potential health condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/protocol">
      <h3>protocol<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/protocol</p>
      <div class="comment">
         <span class="markdown">customized clinical guideline</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/clinical_guideline" title="https://contsys.org/concept/clinical_guideline">clinical guideline</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/reason_for_demand_for_care">
      <h3>reason for demand for care<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/reason_for_demand_for_care</p>
      <div class="comment">
         <span class="markdown">subject of care or a subject of care proxy's perception of health needs motivating a demand for care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/referral">
      <h3>referral<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/referral</p>
      <div class="comment">
         <span class="markdown">demand for care where a healthcare professional asks a healthcare provider to state a healthcare commitment for a care period mandate</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/demand_for_care" title="https://contsys.org/concept/demand_for_care">demandForCare</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/request">
      <h3>request<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/request</p>
      <div class="comment">
         <span class="markdown">demand for care where a healthcare professional asks a healthcare provider to perform one or more healthcare provider activities</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/demand_for_care" title="https://contsys.org/concept/demand_for_care">demandForCare</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_information_request"
               title="https://contsys.org/concept/healthcare_information_request">healthcareInformationRequest</a>
            <sup class="type-c" title="class">c</sup>, <a href="#http://hl7.org/fhir/MedicationRequest" title="http://hl7.org/fhir/MedicationRequest">medication request</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/resource">
      <h3>resource<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/resource</p>
      <div class="comment">
         <span class="markdown">asset that is utilized or consumed during the execution of a process</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Mental-Object">mentalObject</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_funds" title="https://contsys.org/concept/healthcare_funds">healthcare funds</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_resource" title="https://contsys.org/concept/healthcare_resource">healthcare resource</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/resource_delay">
      <h3>resource delay<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/resource_delay</p>
      <div class="comment">
         <span class="markdown">healthcare activity delay caused by resource constraints where there is no health condition delay</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_delay"
               title="https://contsys.org/concept/healthcare_activity_delay">healthcare activity delay</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/resultant_condition">
      <h3>resultant condition<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/resultant_condition</p>
      <div class="comment">
         <span class="markdown">observed condition representing an output health state</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/observed_condition" title="https://contsys.org/concept/observed_condition">observed condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/risk_condition">
      <h3>risk condition<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/risk_condition</p>
      <div class="comment">
         <span class="markdown">potential health condition representing an unintended future health state</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/potential_health_condition"
               title="https://contsys.org/concept/potential_health_condition">potential health condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="http://www.loa-cnr.it/ontologies/DnS#role">
      <h3>role<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://www.loa-cnr.it/ontologies/DnS#role</p>
      <div class="comment">
         <span class="markdown">Also known as 'functional role'. A concept that classifies (in particular, it is 'played by') endurants, as used in some description. Roles are the descriptive counterpart of endurants, and, as endurants participate in perdurants, they usually have courses as modal targets (see). The typology of roles is still preliminary.</span>
      </div>
      <dl class="description">
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_actor" title="https://contsys.org/concept/healthcare_actor">healthcare actor</a>
            <sup class="type-c" title="class">c</sup>, <a href="#d-ontology-781#organizationRole"
               title="http://purl.org/net/for-cocd-ontology-781#organizationRole">organization role</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/party" title="https://contsys.org/concept/party">party</a>
            <sup class="type-c" title="class">c</sup>, <a href="#d-ontology-781#personRole"
               title="http://purl.org/net/for-cocd-ontology-781#personRole">person role</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/self-care_period">
      <h3>self care period<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/self-care_period</p>
      <div class="comment">
         <span class="markdown">healthcare activity period where prescribed self-care is performed</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_period"
               title="https://contsys.org/concept/healthcare_activity_period">healthcare activity period</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/self-care_activity">
      <h3>selfCareActivity<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/self-care_activity</p>
      <div class="comment">
         <span class="markdown">healthcare activity performed by the subject of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity" title="https://contsys.org/concept/healthcare_activity">healthcareActivity</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/prescribed_self-care"
               title="https://contsys.org/concept/prescribed_self-care">prescribed self care</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/service">
      <h3>service<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/service</p>
      <div class="comment">
         <span class="markdown">output of an organization with at least one activity necessarily performed between the organization and the customer</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Event">event</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_service" title="https://contsys.org/concept/healthcare_service">healthcareService</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/sharable_data_repository">
      <h3>sharable data repository<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/sharable_data_repository</p>
      <div class="comment">
         <span class="markdown">data repository containing exclusively electronic health record extracts, accessible for duly authorized healthcare actors independent of their organizational affiliation and placed under the custody of a healthcare actor</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/data_repository" title="https://contsys.org/concept/data_repository">data repository</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/summarized_healthcare_information_repository"
               title="https://contsys.org/concept/summarized_healthcare_information_repository">summarized healthcare information repository</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State">
      <h3>state<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State</p>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Stative"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Stative">stative</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has sub-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/health_need" title="https://contsys.org/concept/health_need">health need</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/health_state" title="https://contsys.org/concept/health_state">health state</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/healthcare_matter" title="https://contsys.org/concept/healthcare_matter">healthcare matter</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/subject_of_care_desire"
               title="https://contsys.org/concept/subject_of_care_desire">subject of care desire</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Stative">
      <h3>stative<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Stative</p>
      <div class="comment">
         <span class="markdown">expressing a state or condition rather than an activity or event</span>
      </div>
      <dl class="description">
         <dt>has sub-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Process"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#Process">process</a>
            <sup class="type-c" title="class">c</sup>, <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State">state</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/subject_of_care_desire">
      <h3>subject of care desire<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/subject_of_care_desire</p>
      <div class="comment">
         <span class="markdown">desire expressed by the subject of care or the subject of care proxy regarding the performance of certain healthcare activities</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State"
               title="http://ontology.ip.rm.cnr.it/ontologies/DOLCE-Lite#State">state</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/subject_of_care_preference_delay">
      <h3>subject of care preference delay<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/subject_of_care_preference_delay</p>
      <div class="comment">
         <span class="markdown">healthcare activity delay by the preference of the subject of care, where there is neither a health condition delay nor a resource delay</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_activity_delay"
               title="https://contsys.org/concept/healthcare_activity_delay">healthcare activity delay</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/subject_of_care_proxy">
      <h3>subject of care proxy<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/subject_of_care_proxy</p>
      <div class="comment">
         <span class="markdown">healthcare third party having person role with the right to take decisions on behalf of the subject of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_third_party"
               title="https://contsys.org/concept/healthcare_third_party">healthcare third party</a>
            <sup class="type-c" title="class">c</sup>, <a href="#d-ontology-781#personRole"
               title="http://purl.org/net/for-cocd-ontology-781#personRole">person role</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/subject_of_care">
      <h3>subjectOfCare<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/subject_of_care</p>
      <div class="comment">
         <span class="markdown">healthcare actor with a person role; who seeks to receive, is receiving, or has received healthcare</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/healthcare_actor" title="https://contsys.org/concept/healthcare_actor">healthcare actor</a>
            <sup class="type-c" title="class">c</sup>, <a href="#d-ontology-781#personRole"
               title="http://purl.org/net/for-cocd-ontology-781#personRole">person role</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
         <dt>has members</dt>
         <dd>
            <a href="#patient1" title="http://purl.org/net/for-coc#patient1">patient1</a>
            <sup class="type-ni" title="named individual">ni</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/summarized_healthcare_information_repository">
      <h3>summarized healthcare information repository<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/summarized_healthcare_information_repository</p>
      <div class="comment">
         <span class="markdown">data repository containing summarized information for healthcare coordination and the continuity of care</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/sharable_data_repository"
               title="https://contsys.org/concept/sharable_data_repository">sharable data repository</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/target_condition">
      <h3>target condition<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/target_condition</p>
      <div class="comment">
         <span class="markdown">potential health condition representing health objectives and/or healthcare goals</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/potential_health_condition"
               title="https://contsys.org/concept/potential_health_condition">potential health condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/uniprofessional_care_plan">
      <h3>uniprofessional care plan<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/uniprofessional_care_plan</p>
      <div class="comment">
         <span class="markdown">care plan limited to those healthcare provider activities performed by healthcare professionals having the same healthcare professional entitlement</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/care_plan" title="https://contsys.org/concept/care_plan">care plan</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
   <div class="entity" id="https://contsys.org/concept/working_diagnosis">
      <h3>working diagnosis<sup class="type-c" title="class">c</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#classes">Class ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/working_diagnosis</p>
      <div class="comment">
         <span class="markdown">considered condition that one or more healthcare professionals have determined to be the most consistent with the currently known observed conditions</span>
      </div>
      <dl class="description">
         <dt>has super-classes</dt>
         <dd>
            <a href="#https://contsys.org/concept/considered_condition"
               title="https://contsys.org/concept/considered_condition">considered condition</a>
            <sup class="type-c" title="class">c</sup>, <a href="#https://contsys.org/concept/professionally_assessed_condition"
               title="https://contsys.org/concept/professionally_assessed_condition">professionally assessed condition</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
</div><div xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="objectproperties">
   <h3 id="properties" class="list">Object Properties</h3>
   <ul class="hlist">
      <li>
         <a href="#componentOf" title="http://purl.org/net/for-coc#componentOf">
            <span>component of</span>
         </a>
      </li>
      <li>
         <a href="#controlsQualityOf" title="http://purl.org/net/for-coc#controlsQualityOf">
            <span>controls quality of</span>
         </a>
      </li>
      <li>
         <a href="#derivesFrom" title="http://purl.org/net/for-coc#derivesFrom">
            <span>derives from</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/MedicationRequest.subject.Reference"
            title="http://hl7.org/fhir/MedicationRequest.subject.Reference">
            <span>medication request.subject. reference</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Observation.basedOn" title="http://hl7.org/fhir/Observation.basedOn">
            <span>observation.based on</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Observation.encounter" title="http://hl7.org/fhir/Observation.encounter">
            <span>observation.encounter</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Observation.performer" title="http://hl7.org/fhir/Observation.performer">
            <span>observation.performer</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Observation.subject" title="http://hl7.org/fhir/Observation.subject">
            <span>observation.subject</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/patient.address.city" title="http://hl7.org/fhir/patient.address.city">
            <span>patient.address.city</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/patient.address.country" title="http://hl7.org/fhir/patient.address.country">
            <span>patient.address.country</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/patient.address.district" title="http://hl7.org/fhir/patient.address.district">
            <span>patient.address.district</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/patient.contact.address.city" title="http://hl7.org/fhir/patient.contact.address.city">
            <span>patient.contact.address.city</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/patient.contact.address.country"
            title="http://hl7.org/fhir/patient.contact.address.country">
            <span>patient.contact.address.country</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/patient.contact.address.district"
            title="http://hl7.org/fhir/patient.contact.address.district">
            <span>patient.contact.address.district</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Patient.contact.organization" title="http://hl7.org/fhir/Patient.contact.organization">
            <span>patient.contact.organization</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/patient.generalpractitioner" title="http://hl7.org/fhir/patient.generalpractitioner">
            <span>patient.generalpractitioner</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Patient.managingOrganization" title="http://hl7.org/fhir/Patient.managingOrganization">
            <span>patient.managing organization</span>
         </a>
      </li>
      <li>
         <a href="#seeksToReceive" title="http://purl.org/net/for-coc#seeksToReceive">
            <span>seeks to receive</span>
         </a>
      </li>
   </ul>
   <div class="entity" id="componentOf">
      <h3>component of<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://purl.org/net/for-coc#componentOf</p>
   </div>
   <div class="entity" id="controlsQualityOf">
      <h3>controls quality of<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://purl.org/net/for-coc#controlsQualityOf</p>
      <div class="description">
         <dl>
            <dt>is inverse of</dt>
            <dd>
               <a href="http://purl.org/net/for-coc#providesFeedbackTo"
                  target="_blank"
                  title="http://purl.org/net/for-coc#providesFeedbackTo">provides feedback to</a>
               <sup class="type-op" title="object property">op</sup>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="derivesFrom">
      <h3>derives from<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://purl.org/net/for-coc#derivesFrom</p>
   </div>
   <div class="entity" id="http://hl7.org/fhir/MedicationRequest.subject.Reference">
      <h3>medication request.subject. reference<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/MedicationRequest.subject.Reference</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topObjectProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topObjectProperty">top object property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Observation.basedOn">
      <h3>observation.based on<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Observation.basedOn</p>
      <div class="comment">
         <span class="markdown">CarePlan|DeviceRequest|ImmunizationRecommendation|MedicationRequest|NutritionOrder|ServiceRequest</span>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Observation.encounter">
      <h3>observation.encounter<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Observation.encounter</p>
      <div class="comment">
         <span class="markdown">Healthcare event during which this observation is made</span>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Observation.performer">
      <h3>observation.performer<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Observation.performer</p>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Observation.subject">
      <h3>observation.subject<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Observation.subject</p>
      <div class="comment">
         <span class="markdown">Who and/or what the observation is about</span>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/patient.address.city">
      <h3>patient.address.city<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/patient.address.city</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topObjectProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topObjectProperty">top object property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/patient.address.country">
      <h3>patient.address.country<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/patient.address.country</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topObjectProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topObjectProperty">top object property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/patient.address.district">
      <h3>patient.address.district<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/patient.address.district</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topObjectProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topObjectProperty">top object property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/patient.contact.address.city">
      <h3>patient.contact.address.city<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/patient.contact.address.city</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topObjectProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topObjectProperty">top object property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/patient.contact.address.country">
      <h3>patient.contact.address.country<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/patient.contact.address.country</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topObjectProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topObjectProperty">top object property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/patient.contact.address.district">
      <h3>patient.contact.address.district<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/patient.contact.address.district</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topObjectProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topObjectProperty">top object property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Patient.contact.organization">
      <h3>patient.contact.organization<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Patient.contact.organization</p>
      <div class="comment">
         <span class="markdown">Organization on behalf of which the contact is acting or for which the contact is working.</span>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/patient.generalpractitioner">
      <h3>patient.generalpractitioner<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/patient.generalpractitioner</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topObjectProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topObjectProperty">top object property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Patient.managingOrganization">
      <h3>patient.managing organization<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Patient.managingOrganization</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topObjectProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topObjectProperty">top object property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="seeksToReceive">
      <h3>seeks to receive<sup class="type-op" title="object property">op</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#objectproperties">Object Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://purl.org/net/for-coc#seeksToReceive</p>
      <div class="comment">
         <span class="markdown">seeks to receive, is receiving, or has received</span>
      </div>
   </div>
</div><div xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="dataproperties">
   <h3 id="dataproperties-headline" class="list">Data Properties</h3>
   <ul class="hlist">
      <li>
         <a href="#https://contsys.org/concept/attachment_value" title="https://contsys.org/concept/attachment_value">
            <span>attachment value</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/attestation_information"
            title="https://contsys.org/concept/attestation_information">
            <span>attestation information</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/base_component" title="https://contsys.org/concept/base_component">
            <span>base component</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/coded_simple_value" title="https://contsys.org/concept/coded_simple_value">
            <span>coded simple value</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/coded_value" title="https://contsys.org/concept/coded_value">
            <span>coded value</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/duration_value" title="https://contsys.org/concept/duration_value">
            <span>duration value</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/MedicationRequest.courseOfTherapyType"
            title="http://hl7.org/fhir/MedicationRequest.courseOfTherapyType">
            <span>medication request.course of therapy type</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/MedicationRequest.dispenseRequest.dispenseInterval"
            title="http://hl7.org/fhir/MedicationRequest.dispenseRequest.dispenseInterval">
            <span>medication request.dispense request.dispense interval</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/MedicationRequest.dispenseRequest.expectedSupplyDuration"
            title="http://hl7.org/fhir/MedicationRequest.dispenseRequest.expectedSupplyDuration">
            <span>medication request.dispense request.expected supply duration</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/MedicationRequest.dispenseRequest.initialFill.Duration"
            title="http://hl7.org/fhir/MedicationRequest.dispenseRequest.initialFill.Duration">
            <span>medication request.dispense request.initial fill. duration</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/MedicationRequest.dispenseRequest.initialFill.quantity"
            title="http://hl7.org/fhir/MedicationRequest.dispenseRequest.initialFill.quantity">
            <span>medication request.dispense request.initial fill.quantity</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/MedicationRequest.dispenseRequest.numberOfRepeatsAllowed"
            title="http://hl7.org/fhir/MedicationRequest.dispenseRequest.numberOfRepeatsAllowed">
            <span>medication request.dispense request.number of repeats allowed</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/MedicationRequest.dispenseRequest.quantity"
            title="http://hl7.org/fhir/MedicationRequest.dispenseRequest.quantity">
            <span>medication request.dispense request.quantity</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/MedicationRequest.dispenseRequest.validityPeriod"
            title="http://hl7.org/fhir/MedicationRequest.dispenseRequest.validityPeriod">
            <span>medication request.dispense request.validity period</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/MedicationRequest.note" title="http://hl7.org/fhir/MedicationRequest.note">
            <span>medication request.note</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/MedicationRequest.status" title="http://hl7.org/fhir/MedicationRequest.status">
            <span>medication request.status</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/MedicationRequest.statusReason"
            title="http://hl7.org/fhir/MedicationRequest.statusReason">
            <span>medication request.status reason</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Observation.code" title="http://hl7.org/fhir/Observation.code">
            <span>observation.code</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Observation.effectiveDateTime"
            title="http://hl7.org/fhir/Observation.effectiveDateTime">
            <span>observation.effective date time</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Observation.identifier" title="http://hl7.org/fhir/Observation.identifier">
            <span>observation.identifier</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Observation.method" title="http://hl7.org/fhir/Observation.method">
            <span>observation.method</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Observation.status" title="http://hl7.org/fhir/Observation.status">
            <span>observation.status</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Observation.value" title="http://hl7.org/fhir/Observation.value">
            <span>observation.value</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Patient.active" title="http://hl7.org/fhir/Patient.active">
            <span>patient.active</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Patient.address.line" title="http://hl7.org/fhir/Patient.address.line">
            <span>patient.address.line</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Patient.communication.language"
            title="http://hl7.org/fhir/Patient.communication.language">
            <span>patient.communication.language</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Patient.contact.address.postalcode"
            title="http://hl7.org/fhir/Patient.contact.address.postalcode">
            <span>patient.contact.address.postalcode</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Patient.contact.gender" title="http://hl7.org/fhir/Patient.contact.gender">
            <span>patient.contact.gender</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Patient.contact.name" title="http://hl7.org/fhir/Patient.contact.name">
            <span>patient.contact.name</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Patient.forename" title="http://hl7.org/fhir/Patient.forename">
            <span>patient.forename</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Patient.gender" title="http://hl7.org/fhir/Patient.gender">
            <span>patient.gender</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Patient.photo" title="http://hl7.org/fhir/Patient.photo">
            <span>patient.photo</span>
         </a>
      </li>
      <li>
         <a href="#http://hl7.org/fhir/Patient.surname" title="http://hl7.org/fhir/Patient.surname">
            <span>patient.surname</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/physical_quantity_value"
            title="https://contsys.org/concept/physical_quantity_value">
            <span>physical quantity value</span>
         </a>
      </li>
      <li>
         <a href="#https://contsys.org/concept/point_in_time_value" title="https://contsys.org/concept/point_in_time_value">
            <span>point in time value</span>
         </a>
      </li>
   </ul>
   <div class="entity" id="https://contsys.org/concept/attachment_value">
      <h3>attachment value<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/attachment_value</p>
      <div class="comment">
         <span class="markdown">data value used for representing information objects that may require special processing operations to be performed in order for the data to be interpreted or rendered</span>
      </div>
   </div>
   <div class="entity" id="https://contsys.org/concept/attestation_information">
      <h3>attestation information<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/attestation_information</p>
      <div class="comment">
         <span class="markdown">base component documenting the details of an attestation of a set of electronic health record components.</span>
      </div>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="#https://contsys.org/concept/base_component" title="https://contsys.org/concept/base_component">base component</a>
               <sup class="type-dp" title="data property">dp</sup>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="https://contsys.org/concept/base_component">
      <h3>base component<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/base_component</p>
      <div class="comment">
         <span class="markdown">abstract class that include the properties common for all revisable classes included in EHR extract</span>
      </div>
      <div class="description">
         <dl>
            <dt>has sub-properties</dt>
            <dd>
               <a href="#https://contsys.org/concept/attestation_information"
                  title="https://contsys.org/concept/attestation_information">attestation information</a>
               <sup class="type-dp" title="data property">dp</sup>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="https://contsys.org/concept/coded_simple_value">
      <h3>coded simple value<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/coded_simple_value</p>
      <div class="comment">
         <span class="markdown">data value used for representing a code in a code system implied and fixed by the context in which this data value occurs</span>
      </div>
   </div>
   <div class="entity" id="https://contsys.org/concept/coded_value">
      <h3>coded value<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/coded_value</p>
      <div class="comment">
         <span class="markdown">data value used for representing a code in a referenced code system</span>
      </div>
   </div>
   <div class="entity" id="https://contsys.org/concept/duration_value">
      <h3>duration value<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/duration_value</p>
      <div class="comment">
         <span class="markdown">data value used for representing a lapse of time</span>
      </div>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="#https://contsys.org/concept/physical_quantity_value"
                  title="https://contsys.org/concept/physical_quantity_value">physical quantity value</a>
               <sup class="type-dp" title="data property">dp</sup>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/MedicationRequest.courseOfTherapyType">
      <h3>medication request.course of therapy type<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/MedicationRequest.courseOfTherapyType</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/MedicationRequest.dispenseRequest.dispenseInterval">
      <h3>medication request.dispense request.dispense interval<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/MedicationRequest.dispenseRequest.dispenseInterval</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/MedicationRequest.dispenseRequest.expectedSupplyDuration">
      <h3>medication request.dispense request.expected supply duration<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/MedicationRequest.dispenseRequest.expectedSupplyDuration</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/MedicationRequest.dispenseRequest.initialFill.Duration">
      <h3>medication request.dispense request.initial fill. duration<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/MedicationRequest.dispenseRequest.initialFill.Duration</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/MedicationRequest.dispenseRequest.initialFill.quantity">
      <h3>medication request.dispense request.initial fill.quantity<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/MedicationRequest.dispenseRequest.initialFill.quantity</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/MedicationRequest.dispenseRequest.numberOfRepeatsAllowed">
      <h3>medication request.dispense request.number of repeats allowed<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/MedicationRequest.dispenseRequest.numberOfRepeatsAllowed</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/MedicationRequest.dispenseRequest.quantity">
      <h3>medication request.dispense request.quantity<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/MedicationRequest.dispenseRequest.quantity</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/MedicationRequest.dispenseRequest.validityPeriod">
      <h3>medication request.dispense request.validity period<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/MedicationRequest.dispenseRequest.validityPeriod</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/MedicationRequest.note">
      <h3>medication request.note<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/MedicationRequest.note</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/MedicationRequest.status">
      <h3>medication request.status<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/MedicationRequest.status</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/MedicationRequest.statusReason">
      <h3>medication request.status reason<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/MedicationRequest.statusReason</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Observation.code">
      <h3>observation.code<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Observation.code</p>
      <div class="description">
         <dl>
            <dt>has range</dt>
            <dd>
               <a href="http://www.w3.org/2000/01/rdf-schema#Literal"
                  target="_blank"
                  title="http://www.w3.org/2000/01/rdf-schema#Literal">literal</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Observation.effectiveDateTime">
      <h3>observation.effective date time<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Observation.effectiveDateTime</p>
      <div class="description">
         <dl>
            <dt>has range</dt>
            <dd>
               <a href="http://www.w3.org/2001/XMLSchema#dateTime"
                  target="_blank"
                  title="http://www.w3.org/2001/XMLSchema#dateTime">date time</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Observation.identifier">
      <h3>observation.identifier<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Observation.identifier</p>
      <div class="comment">
         <span class="markdown">Business Identifier for observation</span>
      </div>
      <div class="description">
         <dl>
            <dt>has range</dt>
            <dd>
               <a href="http://www.w3.org/2000/01/rdf-schema#Literal"
                  target="_blank"
                  title="http://www.w3.org/2000/01/rdf-schema#Literal">literal</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Observation.method">
      <h3>observation.method<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Observation.method</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Observation.status">
      <h3>observation.status<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Observation.status</p>
      <div class="comment">
         <span class="markdown">registered | preliminary | final | amended</span>
      </div>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
            <dt>has range</dt>
            <dd>
               <a href="http://www.w3.org/2000/01/rdf-schema#Literal"
                  target="_blank"
                  title="http://www.w3.org/2000/01/rdf-schema#Literal">literal</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Observation.value">
      <h3>observation.value<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Observation.value</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Patient.active">
      <h3>patient.active<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Patient.active</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
            <dt>has range</dt>
            <dd>
               <a href="http://www.w3.org/2001/XMLSchema#boolean"
                  target="_blank"
                  title="http://www.w3.org/2001/XMLSchema#boolean">boolean</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Patient.address.line">
      <h3>patient.address.line<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Patient.address.line</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Patient.communication.language">
      <h3>patient.communication.language<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Patient.communication.language</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Patient.contact.address.postalcode">
      <h3>patient.contact.address.postalcode<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Patient.contact.address.postalcode</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Patient.contact.gender">
      <h3>patient.contact.gender<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Patient.contact.gender</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Patient.contact.name">
      <h3>patient.contact.name<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Patient.contact.name</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Patient.forename">
      <h3>patient.forename<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Patient.forename</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Patient.gender">
      <h3>patient.gender<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Patient.gender</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Patient.photo">
      <h3>patient.photo<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Patient.photo</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="http://hl7.org/fhir/Patient.surname">
      <h3>patient.surname<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://hl7.org/fhir/Patient.surname</p>
      <div class="description">
         <dl>
            <dt>has super-properties</dt>
            <dd>
               <a href="http://www.w3.org/2002/07/owl#topDataProperty"
                  target="_blank"
                  title="http://www.w3.org/2002/07/owl#topDataProperty">top data property</a>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="https://contsys.org/concept/physical_quantity_value">
      <h3>physical quantity value<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/physical_quantity_value</p>
      <div class="comment">
         <span class="markdown">data value used for representing a quantity expressing the result of a measuring</span>
      </div>
      <div class="description">
         <dl>
            <dt>has sub-properties</dt>
            <dd>
               <a href="#https://contsys.org/concept/duration_value" title="https://contsys.org/concept/duration_value">duration value</a>
               <sup class="type-dp" title="data property">dp</sup>
            </dd>
         </dl>
      </div>
   </div>
   <div class="entity" id="https://contsys.org/concept/point_in_time_value">
      <h3>point in time value<sup class="type-dp" title="data property">dp</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#dataproperties">Data Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> https://contsys.org/concept/point_in_time_value</p>
      <div class="comment">
         <span class="markdown">data value used for representing a point in time with minimum resolution year, and maximum resolution fraction of second</span>
      </div>
   </div>
</div><div xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     id="annotationproperties">
   <h3 id="annotationproperties" class="list">Annotation Properties</h3>
   <ul class="hlist">
      <li>
         <a href="#http://purl.org/dc/elements/1.1/contributor" title="http://purl.org/dc/elements/1.1/contributor">
            <span>contributor</span>
         </a>
      </li>
      <li>
         <a href="#http://purl.org/dc/elements/1.1/creator" title="http://purl.org/dc/elements/1.1/creator">
            <span>creator</span>
         </a>
      </li>
      <li>
         <a href="#http://www.geneontology.org/formats/oboInOwl#hasDbXref"
            title="http://www.geneontology.org/formats/oboInOwl#hasDbXref">database_cross_reference</a>
      </li>
      <li>
         <a href="#http://purl.org/dc/elements/1.1/date" title="http://purl.org/dc/elements/1.1/date">
            <span>date</span>
         </a>
      </li>
      <li>
         <a href="#http://www.w3.org/2004/02/skos/core#example" title="http://www.w3.org/2004/02/skos/core#example">
            <span>example</span>
         </a>
      </li>
      <li>
         <a href="#http://purl.org/dc/terms/license" title="http://purl.org/dc/terms/license">
            <span>license</span>
         </a>
      </li>
      <li>
         <a href="#http://www.w3.org/2004/02/skos/core#note" title="http://www.w3.org/2004/02/skos/core#note">
            <span>note</span>
         </a>
      </li>
      <li>
         <a href="#http://purl.org/dc/elements/1.1/title" title="http://purl.org/dc/elements/1.1/title">
            <span>title</span>
         </a>
      </li>
   </ul>
   <div class="entity" id="http://purl.org/dc/elements/1.1/contributor">
      <h3>contributor<sup class="type-ap" title="annotation property">ap</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#annotationproperties">Annotation Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://purl.org/dc/elements/1.1/contributor</p>
   </div>
   <div class="entity" id="http://purl.org/dc/elements/1.1/creator">
      <h3>creator<sup class="type-ap" title="annotation property">ap</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#annotationproperties">Annotation Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://purl.org/dc/elements/1.1/creator</p>
   </div>
   <div class="entity" id="http://www.geneontology.org/formats/oboInOwl#hasDbXref">
      <h3>database_cross_reference<sup class="type-ap" title="annotation property">ap</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#annotationproperties">Annotation Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://www.geneontology.org/formats/oboInOwl#hasDbXref</p>
   </div>
   <div class="entity" id="http://purl.org/dc/elements/1.1/date">
      <h3>date<sup class="type-ap" title="annotation property">ap</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#annotationproperties">Annotation Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://purl.org/dc/elements/1.1/date</p>
   </div>
   <div class="entity" id="http://www.w3.org/2004/02/skos/core#example">
      <h3>example<sup class="type-ap" title="annotation property">ap</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#annotationproperties">Annotation Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://www.w3.org/2004/02/skos/core#example</p>
   </div>
   <div class="entity" id="http://purl.org/dc/terms/license">
      <h3>license<sup class="type-ap" title="annotation property">ap</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#annotationproperties">Annotation Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://purl.org/dc/terms/license</p>
   </div>
   <div class="entity" id="http://www.w3.org/2004/02/skos/core#note">
      <h3>note<sup class="type-ap" title="annotation property">ap</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#annotationproperties">Annotation Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://www.w3.org/2004/02/skos/core#note</p>
   </div>
   <div class="entity" id="http://purl.org/dc/elements/1.1/title">
      <h3>title<sup class="type-ap" title="annotation property">ap</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#annotationproperties">Annotation Property ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://purl.org/dc/elements/1.1/title</p>
   </div>
</div><div xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="namedindividuals">
   <h3 id="namedindividuals" class="list">Named Individuals</h3>
   <ul class="hlist">
      <li>
         <a href="#patient1" title="http://purl.org/net/for-coc#patient1">
            <span>patient1</span>
         </a>
      </li>
   </ul>
   <div class="entity" id="patient1">
      <h3>patient1<sup class="type-ni" title="named individual">ni</sup>
         <span class="backlink"> back to <a href="#toc">ToC</a> or <a href="#namedindividuals">Named Individual ToC</a>
         </span>
      </h3>
      <p>
         <strong>IRI:</strong> http://purl.org/net/for-coc#patient1</p>
      <dl class="description">
         <dt>belongs to</dt>
         <dd>
            <a href="#https://contsys.org/concept/subject_of_care" title="https://contsys.org/concept/subject_of_care">subjectOfCare</a>
            <sup class="type-c" title="class">c</sup>
         </dd>
      </dl>
   </div>
</div><div id="legend">
<h2>Legend <span class="backlink"> back to <a href="#toc">ToC</a></span></h2>
<div   class="entity">
<sup class="type-c" title="Classes">c</sup>: Classes <br/>
<sup class="type-op" title="Object Properties">op</sup>: Object Properties <br/>
<sup class="type-dp" title="Data Properties">dp</sup>: Data Properties <br/>
<sup class="type-ni" title="Named Individuals">ni</sup>: Named Individuals
</div>
</div>
</div>
    

<!--REFERENCES SECTION-->
  <div id="references">
<h2 id="ref" class="list">References <span class="backlink"> back to <a href="#toc">ToC</a></span></h2>
<span class="markdown">
Add your references here. It is recommended to have them as a list.</span>

</div>
<div id="acknowledgments">
<h2 id="ack" class="list">Acknowledgments <span class="backlink"> back to <a href="#toc">ToC</a></span></h2>
<p>
The authors would like to thank <a href="http://www.essepuntato.it/">Silvio Peroni</a> for developing <a href="http://www.essepuntato.it/lode">LODE</a>, a Live OWL Documentation Environment, which is used for representing the Cross Referencing Section of this document and <a href="https://w3id.org/people/dgarijo">Daniel Garijo</a> for developing <a href="https://github.com/dgarijo/Widoco">Widoco</a>, the program used to create the template used in this documentation.</p>
</div>


</div>
</body>
</html>
         
         
      
    
          
        
      
