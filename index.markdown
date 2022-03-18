---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
# Parsons Practice

<div id="password_checker1-sortableTrash" class="sortable-code"></div> 
<div id="password_checker1-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="password_checker1-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="password_checker1-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "name = input(&quot;Enter your password&quot;)\n" +
    "while name != password:\n" +
    "	print(&quot;Sorry, wrong password&quot;)\n" +
    "if password == name:\n" +
    "	print(&quot;Welcome user&quot;)";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "password_checker1-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": false,
    "trashId": "password_checker1-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#password_checker1-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#password_checker1-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
