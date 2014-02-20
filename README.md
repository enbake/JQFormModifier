<h1>JQUERY FORM MODIFIER</h1>
Jquery form modifier is jquery library that makes easy to dynamically clone elements and change their name on the fly. It is just one light weight file that can do everything for you instead of writing hundered of lines of code for cloning elements and removing.

It will replace numeric value in name/id attribute and add it by 1 to generate new name/id. 

<h1>USAGE</h1>
1. Give a class, lets say, addMoreElem to the wrapper of block to be cloned.
2. Give a ahref with id, lets say addMoreLink, clicking which will clone the element.
3. in jquery initialize form modifier with these attributes.

eg:

    <table>
       <tr class = “addMoreElem”>
           <td class = “formRow”><input id = “name0” name = “name[0]”></td>
           <td class = “formRow”><input id = “age0” name = “age[0]”></td>
           <td class = “formRow”><a href = “#” id = “remove0” name = “remove0” class = “cloneRemove”>Remove</a><td>
       </tr>
    </table>

<div><a href = “#” id = “addMoreLink”>Add More Rows</a></div>

Pass basic params to form-modifier like id/class of element to be cloned.

    $(‘# addMoreLink’).FormModifier({
      cloneElem : ‘.addMoreElem’
      cloneRow : true, 
      isParent : true,
      labelPrefix : null, 
      labelDiv : '', 
      child : ‘.formRow’, 
      formid : ‘FormId’,
      canDeleteLast : false, 
      appendTo : 'e_result'
    });

Append a row

    $(‘# addMoreLink’).live('click', function(e) {
          $(‘# addMoreLink’).data('FormModifier').appendRow();
    }

Delete Row:-

    $(‘.cloneRemove’).live('click', function(e) {
          $(this).closest("tr").remove();
    }

Form modifier works on id and name of input/select/textareas. So, don’t forgot to give id  and name. Both id and name should have number 0.