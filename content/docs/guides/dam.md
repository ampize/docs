---
$title@: Digital assets
$order: 4
isDraft: 1
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >

href: /docs/components/dam
---


Ampize possesses an interface to manage digital assets which came from your data sources or allows you to upload your own images.
Moreover this interface allows you to choose an image for all image type field.
<br>

##Launching the image library


You can access the image library from 2 places : "globally" from the burger menu or on an "image field".


###Globally

<div class="col-6 md-col-3">
	<amp-img src="/static/img/menu-burger.png"  width="227"  height="105"  layout="responsive"  alt="menu burger"></amp-img>
</div>
<div class="col-12 md-col-8">
	<amp-img src="/static/img/image-library/menu-image-library.png"  width="610"  height="340"  layout="responsive"  alt="menu image library"></amp-img>
</div>

###Image Field
<div class="col-12 md-col-8">
	<amp-img src="/static/img/image-library/inline-image-library.png"  width="1422"  height="615"  layout="responsive"  alt="inline image library"></amp-img>
</div>


Lauching the library from the menu make it appear in a page, while launching it from a field make it appear in a modal.

<br>

##Using the library
There is 2 main sections in the library : Search and Import


###Search
<div class="col-12 md-col-8">
	<amp-img src="/static/img/image-library/search-image-library.png"  width="863"  height="547"  layout="responsive"  alt="search image library"></amp-img>
</div>
On the left sidenav you can find all your sources which contains images. The first one is "Uploaded" : images that you manually upload thanks to the import.
The others are all your data sources containing an image field.

<br>

####Selecting a source
<div class="col-12 md-col-8">
	<amp-img src="/static/img/image-library/filter-image-library.png"  width="1179"  height="618"  layout="responsive"  alt="filter image library"></amp-img>
</div>

<br>

Once you have a chosen a source, you can then filter and/or sort images from this source to help you find the asset that you need.
If you had launched the image library from a field you can then choose the image that you want, while if you had launched it globally you can only consult them.


Moreover, images uploaded can be deleted.
<div class="col-6 md-col-4">
	<amp-img src="/static/img/image-library/choose-image-library.png"  width="342"  height="246"  layout="responsive"  alt="select image"></amp-img>
</div>

<br>

###Import
In the import tab you can upload your own images. You just have to drag and drop or select from your compute images that you want to upload and then click on «Import».

<div class="col-12 md-col-8">
	<amp-img src="/static/img/image-library/import-image-library.png"  width="853"  height="498"  layout="responsive"  alt="import image library"></amp-img>
</div>

<br>
Once the upload is finished a green chip appears on each images that have been correctly uploaded. You can now find them on the "Uploaded" source.

<br>

##Note about images
The AMP specification requires that each images must have an explicit size. Hopefully, you dont have to manually set the width and height on each images, Ampize will deduce them automatically for you.