### Priority: High

#### Component: Read uploaded text files

- **As** a manager
- **I can upload** xml files from other systems
- **So** i can update my management site with current stock info

###### Acceptance criteria:

The user can select the file they trough a form in the UI

###### Code to review:
```python 

from xml.dom.pulldom import START_ELEMENT, parseString
import xml

@app.route("/home", methods=['POST', 'GET'])
def upload_xml():
    doc = parseString(request.form['upload_xml'])
    try:
        for event, node in doc:
            if event == START_ELEMENT and node.localName == "items":
                doc.expandNode(node)
                nodes = node.toxml()
        return render_template("index.html", nodes=nodes)
    except (UnboundLocalError, xml.sax._exceptions.SAXParseException):
        return render_template("index.html")
```

XML format used:

```
<items>
  <item name="item1"> item1 </item>
  <item name="item2"> item2 </item>
  <item name="item3"> item3 </item>
  <item name="item4"> item4 </item>
</items>
```