### Priority: High

#### Component: Read uploaded text files

- **As** a site visitor
- **I can view** text files uploaded by users
- **So** i can read the contents

###### Acceptance criteria:

The user can select the file they want to read from a dropdown menu in the GUI.


###### Code to review:
```python 
@app.route("/home", methods=['POST'])
def home():
    filename = request.form['filename']
    if filename == "":
        filename = "default.txt"
    f = open(filename,'r')
    read = f.read()
    return render_template("index.html",read = read)
```

```html
................
..... snip .....
................
		<div class="row">
			<div class="col-lg-12">
				<div class="panel panel-default">
					<div class="panel-heading">Local file inclusion/path traversal</div>
					<div class="panel-body">
						<div class="col-md-6">
							<form method="post" action="/home" enctype="multipart/form-data">
                					<div class="form-group">
									<label>Selects</label>
									<select name="filename" class="form-control">
										<option value="text/intro.txt">Intro</option>
										<option value="text/chapter1.txt">Chapter 1</option>
										<option value="text/chapter2.txt">Chapter 2</option>
									</select>
								</div>
               			    <button class="btn btn-primary" type="submit">Submit Button</button>
               			</div>
						</form>
					</div>
				</div>
			</div><!-- /.col-->
		</div><!-- /.row -->
		
	
     <center> <p style="font-size:2em;"> {% autoescape false %} {{read}} {% endautoescape %} </p></center>
................
..... snip .....
................
```