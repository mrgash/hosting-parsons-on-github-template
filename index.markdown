---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
# Parsons Practice

<div id="first-try-sortableTrash" class="sortable-code"></div> 
<div id="first-try-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="first-try-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="first-try-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "user=input(&quot;Hello&quot;)\n" +
    "if user == &quot;Stuff&quot;:\n" +
    "	print(&quot;eat my shorts&quot;)";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "first-try-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": false,
    "trashId": "first-try-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#first-try-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#first-try-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
