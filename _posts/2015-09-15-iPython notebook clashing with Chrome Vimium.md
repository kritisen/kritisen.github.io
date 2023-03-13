## iPython notebook clashing with Chrome Vimium

I started using [iPython Notebook](http://ipython.org/notebook.html) from Chrome at port http://localhost:8890/ and found that the keyboard shortcuts were not working.

Searched for "iPython Notebook clashing with Chrome" but got no useful results.

Finally, figured out that the problem was that I had [Vimium](https://chrome.google.com/webstore/detail/vimium/dbepggeogbaibhgnhhndojpepiihcmeb?hl=en) installed on Chrome (I always do that first when installing Chrome -- it adds Vim like capability to Chrome)

Turning off Vimium just for IP-s pointing to iPython Notebook now lets me access the Notebook shortcuts (see entry for http://localhost:88*/* in [Vimium settings](http://chrome-extension://dbepggeogbaibhgnhhndojpepiihcmeb/pages/options.html) below). Woohoo!

![enter image description here](https://github.com/ksens/ksens.github.io/blob/master/img/ipynb_chrome_vimium.png?raw=true)

[On the fly deactivation of Vimium](https://github.com/philc/vimium/issues/428) may also be a solution.
