---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
# Parsons Practice

<div id="password checker-sortableTrash" class="sortable-code"></div> 
<div id="password checker-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="password checker-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="password checker-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "name = input(&quot;Enter your password&quot;)\n" +
    "while name != password:\n" +
    "	print(&quot;Sorry, wrong password&quot;)\n" +
    "if password == name:\n" +
    "	print(&quot;Welcome user&quot;)";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "password checker-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": false,
    "trashId": "password checker-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#password checker-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#password checker-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
