******************************************************************************************

Pulsar SurveyDB

Author: Rob Lyon, School of Computer Science & Jodrell Bank Centre for Astrophysics,
		University of Manchester, Kilburn Building, Oxford Road, Manchester M13 9PL.

Web:		http://www.scienceguyrob.com or http://www.cs.manchester.ac.uk
			or alternatively http://www.jb.man.ac.uk
******************************************************************************************

1. Overview

	Simple interactive webpage describing all pulsar surveys conducted since 1968. Uses a jQuery
    plugin to add table interactivity and nice popup dialogs.

2. Adding entries
	
	Adding entries to the table requirs three simple steps.
    
    STEP 1. Adding a new entry to the table(s).
    
        Here is a shortened varsion of the table.

            <table id="spec_table" class="table table-bordered">
                <thead>
                    <tr>
                        <th>Survey</th>
                        <th>Survey Year</th>
                        <th>Telescope</th>
                        <th>Centre Freq. (Mhz)</th>
                        <th>Bandwidth (Mhz)</th>
                        <th>Channel Width (Khz)</th>
                        <th>Channels</th>
                        <th>Sampling (&mu; sec)</th>
                        <th>Integration time (secs)</th>
                        <th>Beams</th>
                        <th>Pointings</th>
                        <th>Region</th>
                        <th>Region Sq. Deg.</th>
                    </tr>
                </thead>
                    <tr>
                        <td>1st Molonglo Survey [<a href="#" onclick="$('#cite_pop_1').popup('show');">1</a>]</td>
                        <td>1968</td>
                        <td><span class="flagicon"><img alt="" src="images/Molonglo_32x32.png" width="22" height="15" class="thumbborder" />&#160;</span>Molonglo</td>
                        <td>408</td>
                        <td>4</td>
                        <td>2000</td>
                        <td>2</td>
                        <td>5000</td>
                        <td>15</td>
                        <td>1</td>
                        <td>?</td>
                        <td>|b| &lt; 10&deg;, |b| &gt; 10&deg;</td>
                        <td>22980</td>
                    </tr>
                </table>

        It contains one row describing the table headers, and one entry describing the molongo survey. The
        first table data (<td></td>) entry describes the survey name. Here we see that listed as the "1st
        Molonglo Survey". Next to this, there is an anchor tag (<a></a>), inside two brackets i.e. [<a></a>].
        This contains the reference to the survey, which opens a new popup with details of the references, e.g.

        <td>1st Molonglo Survey [<a href="#" onclick="$('#cite_pop_1').popup('show');">1</a>]</td>

        This indicates that when the user clicks on the reference next to the survey name, popup "cite_pop_1"
        will open. The third table data element, describes the instrument used for the survey, along with a small
        image of the instrument itself, e.g.

        <td><span class="flagicon"><img alt="" src="images/Molonglo_32x32.png" width="22" height="15" class="thumbborder" />&#160;</span>Molonglo</td>

        To add a new entry, both of these must be updated accordingly. For example for a new imaginary survey "Rob 1", we
        would have to add a new entry as follows:

            <table id="spec_table" class="table table-bordered">
                <thead>
                    <tr>
                        <th>Survey</th>
                        <th>Survey Year</th>
                        <th>Telescope</th>
                        <th>Centre Freq. (Mhz)</th>
                        <th>Bandwidth (Mhz)</th>
                        <th>Channel Width (Khz)</th>
                        <th>Channels</th>
                        <th>Sampling (&mu; sec)</th>
                        <th>Integration time (secs)</th>
                        <th>Beams</th>
                        <th>Pointings</th>
                        <th>Region</th>
                        <th>Region Sq. Deg.</th>
                    </tr>
                </thead>
                    <tr>
                        <td>1st Molonglo Survey [<a href="#" onclick="$('#cite_pop_1').popup('show');">1</a>]</td>
                        <td>1968</td>
                        <td><span class="flagicon"><img alt="" src="images/Molonglo_32x32.png" width="22" height="15" class="thumbborder" />&#160;</span>Molonglo</td>
                        <td>408</td>
                        <td>4</td>
                        <td>2000</td>
                        <td>2</td>
                        <td>5000</td>
                        <td>15</td>
                        <td>1</td>
                        <td>?</td>
                        <td>|b| &lt; 10&deg;, |b| &gt; 10&deg;</td>
                        <td>22980</td>
                    </tr>
                    <tr>
                        <td>Rob 1 [<a href="#" onclick="$('#cite_pop_2').popup('show');">2</a>]</td>
                        <td>2015</td>
                        <td><span class="flagicon"><img alt="" src="images/Parkes_32x32.png" width="22" height="15" class="thumbborder" />&#160;</span>Parkes</td>
                        <td>1420</td>
                        <td>500</td>
                        <td>3000</td>
                        <td>96</td>
                        <td>64</td>
                        <td>?</td>
                        <td>?</td>
                        <td>?</td>
                        <td>?</td>
                        <td>22980</td>
                    </tr>
                </table>

        Here we see a new entry for the "Rob 1" survey, which is apparently being conducted at Parkes. Note that here,

        <td>Rob 1 [<a href="#" onclick="$('#cite_pop_2').popup('show');">2</a>]</td>

        "cite_pop_1" has become "cite_pop_2" - this must be incremented when adding a new survey, i.e. one popup per survey entry.
        Also note that the reference has increased - you have to manage the referencing carefully. What I mean is that if the survey
        Rob 1 was described by two papers, then we would have to do the following:
        
        <td>Rob 1 [<a href="#" onclick="$('#cite_pop_2').popup('show');">2</a> , <a href="#" onclick="$('#cite_pop_3').popup('show');">3</a> ]</td>
        
        So the number referencing is completely in your hands. 
        
        Similarly the image path has changed, from,

        src="images/Molonglo_32x32.png" to src="images/Parkes_32x32.png"

        There are a few images to choose from, select the most appropriate or add your own 32x32 pixel image.

            IMAGES

            Arecibo_128x128.png
            Effelsberg_32x32.png
            FAST_32x32.png
            GBT_32x32.png
            GMRT_32x32.png
            Jodrell_32x32.png
            Lofar_32x32.png
            Molonglo_32x32.png
            Parkes_32x32.png
            SKA_32x32.png
            Westerbork_32x32.png
        
   STEP 2. Adding a new reference popup.
        
        Each entry above has a link to a popup. A new popup has to created from each entry. All popups are actual divs (<div></div>)
        which describe the popup. These divs are invisible, until the user click a reference that corresponds to them.
        
        For instance, for the 1st Molonglo Survey, there is a link to the popup in an anchor element:
        
        <a href="#" onclick="$('#cite_pop_1').popup('show');">1</a>
        
        When this is clicked, the following div is displayed:
        
        <div id="cite_pop_1" class="well"> <!-- Popups 1 -->
            <h4>Citation</h4>
            <pre class="prettyprint">
                <code>@article{Large:1968:mi,
                author  = {{Large}, M.~I. and {Vaughan}, A.~E. and {Wielebinski}, R.},
                title   = {{Pulsar Search at the Molonglo Radio Observatory}},
                journal = {Nature},
                year    = {1968},
                volume  = {220},
                pages   = {753-756},
                doi     = {10.1038/220753a0},
                url     = {http://dx.doi.org/10.1038/220753a0}
                }</code>
            </pre> <a target="_blank" href="http://dx.doi.org/10.1038/220753a0">
                <button class="fade_close fadeandscale_open btn btn-default">Go to Cited Paper</button></a>
                <button onclick="$('#cite_pop_1').popup('hide');" class="fade_close btn btn-default">Close</button>
        </div>
        
        This popup displays bibtex details for the references, and a button linking to the original paper.
        
        To add a new popup describing the imaginary "Rob 1" survey, we simply do the following:
        
        <div id="cite_pop_2" class="well"> <!-- Popups 2 -->
            <h4>Citation</h4>
            <pre class="prettyprint">
                <code>@article{Rob:2015:survey,
                author  = {{Lyon}, R.~J.},
                title   = {{An Amazing New Survey}},
                journal = {Some Journal},
                year    = {2015},
                volume  = {1},
                pages   = {1-5},
                doi     = {00.0000/00000000},
                url     = {http://dx.doi.org/00.0000/00000000}
                }</code>
            </pre> <a target="_blank" href="http://dx.doi.org/00.0000/00000000">
                <button class="fade_close fadeandscale_open btn btn-default">Go to Cited Paper</button></a>
                <button onclick="$('#cite_pop_2').popup('hide');" class="fade_close btn btn-default">Close</button>
        </div>
        
        Note the changes - "cite_pop_1" has become "cite_pop_2", the bibtex details have changed, and finally the link
        to the paper have altered so that,
        
        <a target="_blank" href="http://dx.doi.org/10.1038/220753a0">
        
        has become,
        
        <a target="_blank" href="http://dx.doi.org/00.0000/00000000">
    
    STEP 3. Initialising the popops.
    
        The popups created above need to be initialised. This is done using java script. So for the 1st Molonglo survey,
        this is done simply via, 
        
        <script>
            $(document).ready(function () {

            $('#cite_pop_1').popup({
                transition: 'all 0.3s',
                scrolllock: true
            });
    
            });
        </script>
        
        To intialise the popup for Rob 1, we simply add it here as follows:
        
        <script>
            $(document).ready(function () {

            $('#cite_pop_1').popup({
                transition: 'all 0.3s',
                scrolllock: true
            });
            $('#cite_pop_2').popup({
                transition: 'all 0.3s',
                scrolllock: true
            });
    
            });
        </script>
        
        Simple!
        
3. Acknowledgements

	This work used the Dynatable plugin (http://www.dynatable.com/) to create the interactive table,
    and the jQuery Popup Overlay plugin (http://dev.vast.com/jquery-popup-overlay/) to create reference
    popups. Thanks to both for their work!!
