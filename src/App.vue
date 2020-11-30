

<template>
  <div id="app">
    <h1>This is bmil web creater</h1>

    <b-button :pressed.sync="showMain" variant="outline-primary">showMain</b-button>
    <b-button :pressed.sync="NRFVisible" variant="outline-primary">SSUNRF</b-button>
    <b-button :pressed.sync="ITRCVisible" variant="outline-primary">SSUITRC</b-button>
    <b-button :pressed.sync="IITPVisible" variant="outline-primary">EWHAIITP</b-button>

    <p>Pressed State: <strong>{{ showMain }}, {{NRFVisible}}, {{ITRCVisible}},{{IITPVisible}} </strong></p>
    <h5 class="mt-3">Weighted Button</h5>
    <b-button :pressed.sync="isWeighted" variant="outline-primary">Weight</b-button>
    <p>Pressed State: <strong>{{ isWeighted }}</strong></p>
    <b-button :pressed.sync="isPatent" variant="outline-primary">Patent</b-button>
    <p>Pressed State: <strong>{{ isPatent }}</strong></p>



    <!--<ul v-for="item in users" v-if="!isWeighted&&isVisible&&showMain">-->

      <!--&lt;!&ndash;<li v-if="item.titleLink">{{item.authorsToString}}<b-link v-if="item.titleLink" v-bind:href='item.titleLink' >  "{{item.title}},"</b-link>  <b>{{item.academyName}}</b> <b v-if="item.vol"> vol.{{item.vol}},</b>  <b v-if="item.no"> no.{{item.no}},</b> <b v-if="item.pp"> pp.{{item.pp}},</b> <b v-if="item.상태&&item.상태!='published'">{{item.상태}}</b> {{item.month}} {{item.year}}. <b-link v-if="item.PDF" v-bind:href="item.PDF">[PDF]</b-link>   <b-link v-if="item.Video" v-bind:href="item.Video">[Video]</b-link>   <b-link v-if="item.Slides" v-bind:href="item.Slides">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv">[arXiv]</b-link> {{item.비고}}</li>&ndash;&gt;-->
      <!--<li > {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b></li>-->

      <!--&lt;!&ndash;<li v-else>{{item.authorsToString}}"{{item.title}}" <b>{{item.academyName}}</b>   {{item.상태}}   <b-link v-if="item.PDF" v-bind:href="item.PDF">[PDF]</b-link>,  <b-link v-if="item.arXiv" v-bind:href="item.arXiv">[arXiv]</b-link> {{item.비고}}</li>&ndash;&gt;-->
    <!--</ul>-->

    <!--<ul v-for="item in users" v-if="isWeighted&&isVisible&&showMain">-->

      <!--<li v-if="item.weighted&&item.titleLink">{{item.authorsToString}} <span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href='item.titleLink' target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span>  <b>{{item.academyName}}</b>, <b v-if="item.vol"> vol.{{item.vol}},</b>  <b v-if="item.no"> no.{{item.no}},</b> <b v-if="item.pp"> pp.{{item.pp}},</b> <b v-if="item.상태&&item.상태!='published'">{{item.상태}}</b> {{item.month}} {{item.year}}. <b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link>   <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link>   <b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b></li>-->
      <!--<li v-else-if="item.weighted">{{item.authorsToString}}"{{item.title}}," <b>{{item.academyName}}</b>,{{item.상태}} {{item.month}} {{item.year}}. <b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF],</b-link>  <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link> <b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b></li>-->
      <!---->
    <!--</ul>-->

    <!--<ul v-for="item in users" v-if="isPatent&&isPatentVisible&&showMain">-->

      <!--<li  v-if="(item.patents)&&((item.type=='미국특허등록'))">  {{item.authorsToString}}  <span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href='item.titleLink' target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span> <span v-if="!item.titleLink"> "{{item.title}},"</span> US Patent, {{item.month}} {{item.day}}, {{item.year}}<span v-if="!item.issuedNo">.</span> (Application no. {{item.patents}})<span v-if="item.issuedNo">, issued on  {{item.iss_month}} {{item.iss_day}}, {{item.iss_year}}. (Patent no. {{item.issuedNo}})</span>{{item.비고}}</li>-->
    <!--</ul>-->


    <!--<ul v-for="item in users" v-if="isPatent&&isPatentVisible&&showMain">-->

      <!--<li  v-if="(item.patents)&&((item.type=='PCT출원'))">  {{item.authorsToString}}  <span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href='item.titleLink' target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span> <span v-if="!item.titleLink"> "{{item.title}},"</span> PCT, {{item.month}} {{item.day}}, {{item.year}}<span v-if="!item.issuedNo">.</span> (Application no. {{item.patents}})<span v-if="item.issuedNo">, issued on  {{item.iss_month}} {{item.iss_day}}, {{item.iss_year}}. (Patent no. {{item.issuedNo}})</span>{{item.비고}}</li>-->
    <!--</ul>-->

    <!--<ul v-for="(data, index) in makeKrIssPatentArr" v-if="isPatent&&isPatentVisible&&showMain">-->
      <!--<li  v-if="((index < data.length)&&(data[index]['SSUNRF']!=0))" >  {{data[index]["authorsToString"]}}  <span v-if="data[index]['titleLink']">"</span><b-link v-if="data[index]['titleLink']" v-bind:href="data[index]['titleLink']" target="_blank">{{data[index]['title']}}</b-link><span v-if="data[index]['titleLink']">,"</span> <span v-if="!data[index]['titleLink']"> "{{data[index]['title']}},"</span>Korean Patent, filed on {{data[index]['month']}}, {{data[index]['day']}}, {{data[index]['year']}} (Application no. {{data[index]['patents']}})<span v-if="data[index]['issuedNo']">, issued on  {{data[index]['iss_month']}} {{data[index]['iss_day']}}, {{data[index]['iss_year']}}. (Patent no. {{data[index]['issuedNo']}})</span>{{data[index]['비']}}</li>-->
    <!--</ul>-->


    <!--<ul v-for="(data, index) in makeSwArr" v-if="isPatent&&isPatentVisible&&showMain">-->
      <!--<li v-if="((index < data.length)&&(data[index]['SSUNRF']!=0))"> {{data[index]["authorsToString"]}}"{{data[index]["title"]}},"Korea Copyright Commission, {{data[index]['month']}}. {{data[index]['day']}}, {{data[index]['year']}}. (Registration no. {{data[index]['patents']}})</li>-->
    <!--</ul>-->

    <!--<ul v-for="item in users " v-if="!showMain&&NRFVisible" >-->
      <!--<li  v-if="item.SSUNRF">     {{item.type}}, {{item.authorsToString}}  "{{item.title}}" <b>{{item.academyName}}</b> <b v-if="item.상태!=='published'">{{item.상태}}</b>, {{item.SSUNRF}}, {{item.비고}}</li>-->
    <!--</ul>-->

    <!--<ul v-for="item in users " v-if="!showMain&&ITRCVisible" >-->

      <!--<li  v-if="item.SSUITRC">    {{item.type}},  {{item.authorsToString}}  "{{item.title}}" <b>{{item.academyName}}</b> <b v-if="item.상태!=='published'"> {{item.상태}}</b> , {{item.SSUITRC}}, {{item.비고}}</li>-->

    <!--</ul>-->

    <!--<ul v-for="item in users " v-if="!showMain&&IITPVisible">-->

      <!--<li  v-if="item.EWHAIITP">    {{item.type}},  {{item.authorsToString}}  "{{item.title}}" <b>{{item.academyName}}</b> <b v-if="item.상태!=='published'"> {{item.상태}} </b>, {{item.EWHAIITP}}, {{item.비고}}</li>-->

    <!--</ul>-->


    <!--<p><b>SCI(E) Journals</b></p>-->
    <!--<br>-->
    <!--<dl v-for="(data, index) in makeSciArr">-->
      <!--&lt;!&ndash;<dt v-if="(index < data.length)&&(yearCalc(index, data.length, makeSciArr)) "> {{data[index]["year"]}}</dt>&ndash;&gt;-->
      <!--<ul >-->
        <!--<li v-if="((index < data.length)&&(data[index]['SSUNRF']!=0))"> {{data[index]["authorsToString"]}}<span v-if="data[index]['titleLink']">"</span><b-link v-if="data[index]['titleLink']" v-bind:href="data[index]['titleLink']">{{data[index]["title"]}}</b-link><span v-if="data[index]['titleLink']">,"</span><span v-if="!data[index]['titleLink']">"{{data[index]["title"]}},"</span> <b>{{data[index]["academyName"]}}</b>, <span v-if="data[index]['vol']">vol.{{data[index]['vol']}},</span>  <span v-if="data[index]['no']"> no.{{data[index]['no']}},</span> <span v-if="data[index]['pp']"> pp.{{data[index]['pp']}},</span> <span v-if="data[index]['상태']&&data[index]['상태']!='published'">{{data[index]['상태']}}</span>{{data[index]['month']}} {{data[index]['year']}}. <b-link v-if="data[index]['PDF']" v-bind:href="data[index]['PDF']">[PDF]</b-link> <b-link v-if="data[index]['Video']" v-bind:href="data[index]['Video']">[Video]</b-link><b-link v-if="data[index]['Slides']" v-bind:href="data[index]['Slides']">[Slides]</b-link> <b-link v-if="data[index]['arXiv']" v-bind:href="data[index]['arXiv']">[arXiv]</b-link><b>{{data[index]['비고']}}</b></li>-->
      <!--</ul>-->
    <!--</dl>-->
    <!--<br>-->

    <span v-if="!isWeighted&&isVisible&&showMain"><p><b>SCI(E) Journals</b></p></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makeSciArr)" v-if="!isWeighted&&isVisible&&showMain">
      <li > {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b></li>

    </ul>
    <br>

    <span v-if="!isWeighted&&isVisible&&showMain"><p><b>International Conferences</b></p></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makeIcfArr)" v-if="!isWeighted&&isVisible&&showMain">
      <li > {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b></li>
    </ul>
    <br>


    <span v-if="!isWeighted&&isVisible&&showMain"><p><b>Machine Learning Workshop Papaers/ Neuroscience Conference Abstracts</b></p></span>
    <ul v-for="(item, index) in sortByDate(makeWsArr)" v-if="!isWeighted&&isVisible&&showMain">
      <li > {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b></li>
    </ul>
    <br>

    <span v-if="!isWeighted&&isVisible&&showMain"><P><b>Domestic Journal Articles</b></P></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makeKciArr)" v-if="!isWeighted&&isVisible&&showMain">
      <li > {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b></li>
    </ul>
    <br>

    <span v-if="!isWeighted&&isVisible&&showMain"><p><b>Domestic Conference Proceedings</b></p></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makeKcfArr)" v-if="!isWeighted&&isVisible&&showMain">
      <li > {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b></li>
    </ul>
    <br>

    <span v-if="!isWeighted&&isVisible&&showMain"><p><b>미국특허등록</b></p></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makeUsPatentArr)" v-if="!isWeighted&&isVisible&&showMain">
      <li >  {{item.authorsToString}}  <span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span> <span v-if="!item.titleLink"> "{{item.title}},"</span>US Patent, {{item.month}}, {{item.day}}, {{item.year}} (Application no. {{item.patents}})<span v-if="item.issuedNo">, issued on  {{item.iss_month}} {{item.iss_day}}, {{item.iss_year}}. (Patent no. {{item.issuedNo}})</span>{{item.비고}}</li>
    </ul>
    <br>

    <span v-if="!isWeighted&&isVisible&&showMain"><p><b>PCT특허등록</b></p></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makePctPatentArr)" v-if="!isWeighted&&isVisible&&showMain">
      <li >  {{item.authorsToString}}  <span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span> <span v-if="!item.titleLink"> "{{item.title}},"</span> PCT, {{item.month}}, {{item.day}}, {{item.year}} (Application no. {{item.patents}})<span v-if="item.issuedNo">, issued on  {{item.iss_month}} {{item.iss_day}}, {{item.iss_year}}. (Patent no. {{item.issuedNo}})</span>{{item.비고}}</li>
    </ul>
    <br>

    <span v-if="!isWeighted&&isVisible&&showMain"><p><b>국내특허등록</b></p></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makeKrIssPatentArr)" v-if="!isWeighted&&isVisible&&showMain">
        <li >  {{item.authorsToString}}  <span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span> <span v-if="!item.titleLink"> "{{item.title}},"</span>Korean Patent, filed on {{item.month}}, {{item.day}}, {{item.year}} (Application no. {{item.patents}})<span v-if="item.issuedNo">, issued on  {{item.iss_month}} {{item.iss_day}}, {{item.iss_year}}. (Patent no. {{item.issuedNo}})</span>{{item.비고}}</li>

    </ul>
    <br>

    <span v-if="!isWeighted&&isVisible&&showMain"><p><b>Software Registrations</b></p></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makeSwArr)" v-if="!isWeighted&&isVisible&&showMain">
      <li>  {{item.authorsToString}}"{{item.title}}," Korea Copyright Commission, {{item.month}} {{item.day}}, {{item.year}}. (Registration no. {{item.patents}})</li>
    </ul>
    <br>

  <span v-if="isWeighted&&isVisible&&showMain">
  <br>
  ================================
    <br>

    weighted
    <br>
 =================================
    <br>
  </span>


    <span v-if="isWeighted&&isVisible&&showMain"><p><b>SCI(E) Journals</b></p></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makeSciArr)" v-if="isWeighted&&isVisible&&showMain">
      <li v-if="item.weighted"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b></li>

    </ul>
    <br>

    <span v-if="isWeighted&&isVisible&&showMain"><p><b>International Conferences</b></p></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makeIcfArr)" v-if="isWeighted&&isVisible&&showMain">
      <li v-if="item.weighted"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b></li>
    </ul>
    <br>


    <span v-if="isWeighted&&isVisible&&showMain"><p><b>Machine Learning Workshop Papaers/ Neuroscience Conference Abstracts</b></p></span>
    <ul v-for="(item, index) in sortByDate(makeWsArr)" v-if="isWeighted&&isVisible&&showMain">
      <li v-if="item.weighted"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b></li>
    </ul>
    <br>

    <span v-if="isWeighted&&isVisible&&showMain"><P><b>Domestic Journal Articles</b></P></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makeKciArr)" v-if="isWeighted&&isVisible&&showMain">
      <li v-if="item.weighted"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b></li>
    </ul>
    <br>

    <span v-if="isWeighted&&isVisible&&showMain"><p><b>Domestic Conference Proceedings</b></p></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makeKcfArr)" v-if="isWeighted&&isVisible&&showMain">
      <li v-if="item.weighted"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b></li>
    </ul>
    <br>

    <span v-if="isWeighted&&isVisible&&showMain"><p><b>미국특허등록</b></p></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makeUsPatentArr)" v-if="isWeighted&&isVisible&&showMain">
      <li v-if="item.weighted">  {{item.authorsToString}}  <span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span> <span v-if="!item.titleLink"> "{{item.title}},"</span>US Patent, {{item.month}}, {{item.day}}, {{item.year}} (Application no. {{item.patents}})<span v-if="item.issuedNo">, issued on  {{item.iss_month}} {{item.iss_day}}, {{item.iss_year}}. (Patent no. {{item.issuedNo}})</span>{{item.비고}}</li>
    </ul>
    <br>

    <span v-if="isWeighted&&isVisible&&showMain"><p><b>PCT특허등록</b></p></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makePctPatentArr)" v-if="isWeighted&&isVisible&&showMain">
      <li v-if="item.weighted">  {{item.authorsToString}}  <span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span> <span v-if="!item.titleLink"> "{{item.title}},"</span> PCT, {{item.month}}, {{item.day}}, {{item.year}} (Application no. {{item.patents}})<span v-if="item.issuedNo">, issued on  {{item.iss_month}} {{item.iss_day}}, {{item.iss_year}}. (Patent no. {{item.issuedNo}})</span>{{item.비고}}</li>
    </ul>
    <br>

    <span v-if="isWeighted&&isVisible&&showMain"><p><b>국내특허등록</b></p></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makeKrIssPatentArr)" v-if="isWeighted&&isVisible&&showMain">
      <li v-if="item.weighted">  {{item.authorsToString}}  <span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span> <span v-if="!item.titleLink"> "{{item.title}},"</span>Korean Patent, filed on {{item.month}}, {{item.day}}, {{item.year}} (Application no. {{item.patents}})<span v-if="item.issuedNo">, issued on  {{item.iss_month}} {{item.iss_day}}, {{item.iss_year}}. (Patent no. {{item.issuedNo}})</span>{{item.비고}}</li>
    </ul>
    <br>

    <span v-if="isWeighted&&isVisible&&showMain"><p><b>Software Registrations</b></p></span>
    <br>
    <ul v-for="(item, index) in sortByDate(makeSwArr)" v-if="isWeighted&&isVisible&&showMain">
      <li v-if="item.weighted">  {{item.authorsToString}}"{{item.title}}," Korea Copyright Commission, {{item.month}} {{item.day}}, {{item.year}}. (Registration no. {{item.patents}})</li>
    </ul>
    <br>

    <!--과제 추가하려면 여기서부터 복사하면 됩니다.-->
    <p>
    =======================================================
      <br>

    NRF

      <br>
      =====================================================
    </p>

    <span v-if="!showMain&&NRFVisible"><p><b>Journal Articles</b></p></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeSciArr)" v-if="!showMain&&NRFVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeSciArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.SSUNRF"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b>  <span v-if="item.SSUNRF">SSUNRF : {{item.SSUNRF}}</span></li>
      </ul>
    </dl>
    <br>

    <span v-if="!showMain&&NRFVisible"><p><b>International Conferences</b></p></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeIcfArr)" v-if="!showMain&&NRFVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeIcfArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.SSUNRF"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUNRF">SSUNRF : {{item.SSUNRF}}</span></li>
      </ul>
    </dl>
    <br>


    <span v-if="!showMain&&NRFVisible"><p><b>Machine Learning Workshop Papaers/ Neuroscience Conference Abstracts</b></p></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeWsArr)" v-if="!showMain&&NRFVisible">
    <dt v-if="(yearChangeDetect(index,sortByDate(makeWsArr) )) "> {{item.year}}</dt>
    <ul >
      <li v-if="item.SSUNRF"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUNRF">SSUNRF : {{item.SSUNRF}}</span></li>
    </ul>
   </dl>
    <br>

    <span v-if="!showMain&&NRFVisible"><P><b>Domestic Journal Articles</b></P></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeKciArr)" v-if="!showMain&&NRFVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeKciArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.SSUNRF"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUNRF">SSUNRF : {{item.SSUNRF}}</span></li>
      </ul>
    </dl>
    <br>

    <span v-if="!showMain&&NRFVisible"><p><b>Domestic Conference Proceedings</b></p></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeKcfArr)" v-if="!showMain&&NRFVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeKcfArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.SSUNRF"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUNRF">SSUNRF : {{item.SSUNRF}}</span></li>
      </ul>
    </dl>
    <br>

    <span v-if="!showMain&&NRFVisible"><p><b>국내특허등록</b></p></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeKrIssPatentArr)" v-if="!showMain&&NRFVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeKrIssPatentArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.SSUNRF"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUNRF">SSUNRF : {{item.SSUNRF}}</span></li>
      </ul>
    </dl>
    <br>


    <span v-if="!showMain&&NRFVisible"><p><b>Software Registrations</b></p></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeSwArr)" v-if="!showMain&&NRFVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeSwArr) ))"> {{item.year}}</dt>
      <ul >
        <li v-if="item.SSUNRF">  {{item.authorsToString}}"{{item.title}}," Korea Copyright Commission, {{item.month}} {{item.day}}, {{item.year}}. (Registration no. {{item.patents}}) <span v-if="item.SSUNRF">SSUNRF : {{item.SSUNRF}}</span></li>
      </ul>
    </dl>
    <br>

    <!--=====================-->
    <!--NRF END  // 과제 추가시 여기까지 복사하면됩니다-->
    <!--=====================-->



    <p>
    =======================================================
      <br>
    SSUITRC
      <br>
    =======================================================
    </p>

    <span v-if="!showMain&&ITRCVisible"><p><b>Journal Articles</b></p></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeSciArr)" v-if="!showMain&&ITRCVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeSciArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.SSUITRC"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUITRC">SSUITRC : {{item.SSUITRC}}</span></li>
      </ul>
    </dl>
    <br>

    <span v-if="!showMain&&ITRCVisible"><p><b>International Conferences</b></p></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeIcfArr)" v-if="!showMain&&ITRCVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeIcfArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.SSUITRC"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUITRC">SSUITRC : {{item.SSUITRC}}</span></li>
      </ul>
    </dl>
    <br>


    <span v-if="!showMain&&ITRCVisible"><p><b>Machine Learning Workshop Papaers/ Neuroscience Conference Abstracts</b></p></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeWsArr)" v-if="!showMain&&ITRCVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeWsArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.SSUITRC"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUITRC">SSUITRC : {{item.SSUITRC}}</span></li>
      </ul>
    </dl>
    <br>

    <span v-if="!showMain&&ITRCVisible"><P><b>Domestic Journal Articles</b></P></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeKciArr)" v-if="!showMain&&ITRCVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeKciArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.SSUITRC"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUITRC">SSUITRC : {{item.SSUITRC}}</span></li>
      </ul>
    </dl>
    <br>

    <span v-if="!showMain&&ITRCVisible"><p><b>Domestic Conference Proceedings</b></p></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeKcfArr)" v-if="!showMain&&ITRCVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeKcfArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.SSUITRC"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUITRC">SSUITRC : {{item.SSUITRC}}</span></li>
      </ul>
    </dl>
    <br>

    <span v-if="!showMain&&ITRCVisible"><p><b>국내특허등록</b></p></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeKrIssPatentArr)" v-if="!showMain&&ITRCVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeKrIssPatentArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.SSUITRC"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUITRC">SSUITRC : {{item.SSUITRC}}</span></li>
      </ul>
    </dl>
    <br>

    <span v-if="!showMain&&ITRCVisible"><p><b>Software Registrations</b></p></span>
    <br>

    <dl v-for="(item, index) in sortByDate(makeSwArr)" v-if="!showMain&&ITRCVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeSwArr) ))"> {{item.year}}</dt>
      <ul >
        <li v-if="item.SSUITRC">  {{item.authorsToString}}"{{item.title}}," Korea Copyright Commission, {{item.month}} {{item.day}}, {{item.year}}. (Registration no. {{item.patents}}) <span v-if="item.SSUITRC">SSUITRC : {{item.SSUITRC}}</span></li>
      </ul>
    </dl>
    <br>



    <p>
      =======================================================
      <br>
      EWHAIITP
      <br>
      =======================================================
    </p>

    <span v-if="!showMain&&IITPVisible"><p><b>Journal Articles</b></p></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeSciArr)" v-if="!showMain&&IITPVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeSciArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.EWHAIITP"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.EWHAIITP">EWHAIITP : {{item.EWHAIITP}}</span></li>
      </ul>
    </dl>
    <br>

    <span v-if="!showMain&&IITPVisible"><p><b>International Conferences</b></p></span>

    <br>
    <dl v-for="(item, index) in sortByDate(makeIcfArr)" v-if="!showMain&&IITPVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeIcfArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.EWHAIITP"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.EWHAIITP">EWHAIITP : {{item.EWHAIITP}}</span></li>
      </ul>
    </dl>
    <br>


    <span v-if="!showMain&&IITPVisible"><p><b>Machine Learning Workshop Papaers/ Neuroscience Conference Abstracts</b></p></span>

    <br>
    <dl v-for="(item, index) in sortByDate(makeWsArr)" v-if="!showMain&&IITPVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeWsArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.EWHAIITP"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.EWHAIITP">EWHAIITP : {{item.EWHAIITP}}</span></li>
      </ul>
    </dl>
    <br>

    <span v-if="!showMain&&IITPVisible"><P><b>Domestic Journal Articles</b></P></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeKciArr)" v-if="!showMain&&IITPVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeKciArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.EWHAIITP"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.EWHAIITP">EWHAIITP : {{item.EWHAIITP}}</span></li>
      </ul>
    </dl>
    <br>

    <span v-if="!showMain&&IITPVisible"><p><b>Domestic Conference Proceedings</b></p></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeKcfArr)" v-if="!showMain&&IITPVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeKcfArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.EWHAIITP"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.EWHAIITP">EWHAIITP : {{item.EWHAIITP}}</span></li>
      </ul>
    </dl>
    <br>

    <span v-if="!showMain&&IITPVisible"><p><b>국내특허등록</b></p></span>
    <br>
    <dl v-for="(item, index) in sortByDate(makeKrIssPatentArr)" v-if="!showMain&&IITPVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeKrIssPatentArr) )) "> {{item.year}}</dt>
      <ul >
        <li v-if="item.EWHAIITP"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.EWHAIITP">EWHAIITP : {{item.EWHAIITP}}</span></li>
      </ul>
    </dl>
    <br>

    <span v-if="!showMain&&IITPVisible"><p><b>Software Registrations</b></p></span>
    <br>
    <br>

    <dl v-for="(item, index) in sortByDate(makeSwArr)" v-if="!showMain&&IITPVisible">
      <dt v-if="(yearChangeDetect(index,sortByDate(makeSwArr) ))"> {{item.year}}</dt>
      <ul >
        <li v-if="item.EWHAIITP">  {{item.authorsToString}}"{{item.title}}," Korea Copyright Commission, {{item.month}} {{item.day}}, {{item.year}}. (Registration no. {{item.patents}}) <span v-if="item.EWHAIITP">EWHAIITP : {{item.EWHAIITP}}</span></li>
      </ul>
    </dl>
    <br>






    <!--<p>-->
      <!--=======================================================-->
      <!--<br>-->

      <!--과제 추가시 샘플입니다-->
      <!--item.SSUNRF ->  item.sampleSubject  // 엑셀에 추가한 과제 이름 -->
      <!--NRFVisivle -> SampleVisible  // data에 추가한 변수 이름 -->
      <!--한번에 주석 해제 하면됩니다. 보통 코드 편집기에서 command + /-->

      <!--<br>-->
      <!--=====================================================-->
    <!--</p>-->

    <!--<span v-if="!showMain&&NRFVisible"><p><b>Journal Articles</b></p></span>-->
    <!--<br>-->
    <!--<dl v-for="(item, index) in sortByDate(makeSciArr)" v-if="!showMain&&NRFVisible">-->
      <!--<dt v-if="(yearChangeDetect(index,sortByDate(makeSciArr) )) "> {{item.year}}</dt>-->
      <!--<ul >-->
        <!--<li v-if="item.SSUNRF"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b>  <span v-if="item.SSUNRF">SSUNRF : {{item.SSUNRF}}</span></li>-->
      <!--</ul>-->
    <!--</dl>-->
    <!--<br>-->

    <!--<span v-if="!showMain&&NRFVisible"><p><b>International Conferences</b></p></span>-->
    <!--<br>-->
    <!--<dl v-for="(item, index) in sortByDate(makeIcfArr)" v-if="!showMain&&NRFVisible">-->
      <!--<dt v-if="(yearChangeDetect(index,sortByDate(makeIcfArr) )) "> {{item.year}}</dt>-->
      <!--<ul >-->
        <!--<li v-if="item.SSUNRF"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUNRF">SSUNRF : {{item.SSUNRF}}</span></li>-->
      <!--</ul>-->
    <!--</dl>-->
    <!--<br>-->


    <!--<span v-if="!showMain&&NRFVisible"><p><b>Machine Learning Workshop Papaers/ Neuroscience Conference Abstracts</b></p></span>-->
    <!--<br>-->
    <!--<dl v-for="(item, index) in sortByDate(makeWsArr)" v-if="!showMain&&NRFVisible">-->
      <!--<dt v-if="(yearChangeDetect(index,sortByDate(makeWsArr) )) "> {{item.year}}</dt>-->
      <!--<ul >-->
        <!--<li v-if="item.SSUNRF"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUNRF">SSUNRF : {{item.SSUNRF}}</span></li>-->
      <!--</ul>-->
    <!--</dl>-->
    <!--<br>-->

    <!--<span v-if="!showMain&&NRFVisible"><P><b>Domestic Journal Articles</b></P></span>-->
    <!--<br>-->
    <!--<dl v-for="(item, index) in sortByDate(makeKciArr)" v-if="!showMain&&NRFVisible">-->
      <!--<dt v-if="(yearChangeDetect(index,sortByDate(makeKciArr) )) "> {{item.year}}</dt>-->
      <!--<ul >-->
        <!--<li v-if="item.SSUNRF"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUNRF">SSUNRF : {{item.SSUNRF}}</span></li>-->
      <!--</ul>-->
    <!--</dl>-->
    <!--<br>-->

    <!--<span v-if="!showMain&&NRFVisible"><p><b>Domestic Conference Proceedings</b></p></span>-->
    <!--<br>-->
    <!--<dl v-for="(item, index) in sortByDate(makeKcfArr)" v-if="!showMain&&NRFVisible">-->
      <!--<dt v-if="(yearChangeDetect(index,sortByDate(makeKcfArr) )) "> {{item.year}}</dt>-->
      <!--<ul >-->
        <!--<li v-if="item.SSUNRF"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUNRF">SSUNRF : {{item.SSUNRF}}</span></li>-->
      <!--</ul>-->
    <!--</dl>-->
    <!--<br>-->

    <!--<span v-if="!showMain&&NRFVisible"><p><b>국내특허등록</b></p></span>-->
    <!--<br>-->
    <!--<dl v-for="(item, index) in sortByDate(makeKrIssPatentArr)" v-if="!showMain&&NRFVisible">-->
      <!--<dt v-if="(yearChangeDetect(index,sortByDate(makeKrIssPatentArr) )) "> {{item.year}}</dt>-->
      <!--<ul >-->
        <!--<li v-if="item.SSUNRF"> {{item.authorsToString}}<span v-if="item.titleLink">"</span><b-link v-if="item.titleLink" v-bind:href="item.titleLink" target="_blank">{{item.title}}</b-link><span v-if="item.titleLink">,"</span><span v-if="!item.titleLink">"{{item.title}},"</span> <b>{{item.academyName}}</b>, <span v-if="item.vol">vol.{{item.vol}},</span>  <span v-if="item.no"> no.{{item.no}},</span> <span v-if="item.pp"> pp.{{item.pp}},</span> <span v-if="item.상태&&item.상태!='published'">{{item.상태}}</span>{{item.month}} {{item.year}}. <span v-if="item.IF">IF:{{item.IF}}({{item.IF기준년도}})</span><b-link v-if="item.PDF" v-bind:href="item.PDF" target="_blank">[PDF]</b-link> <b-link v-if="item.Video" v-bind:href="item.Video" target="_blank">[Video]</b-link><b-link v-if="item.Slides" v-bind:href="item.Slides" target="_blank">[Slides]</b-link> <b-link v-if="item.arXiv" v-bind:href="item.arXiv" target="_blank">[arXiv]</b-link> <b>{{item.비고}}</b> <span v-if="item.SSUNRF">SSUNRF : {{item.SSUNRF}}</span></li>-->
      <!--</ul>-->
    <!--</dl>-->
    <!--<br>-->


    <!--<span v-if="!showMain&&NRFVisible"><p><b>Software Registrations</b></p></span>-->
    <!--<br>-->
    <!--<dl v-for="(item, index) in sortByDate(makeSwArr)" v-if="!showMain&&NRFVisible">-->
      <!--<dt v-if="(yearChangeDetect(index,sortByDate(makeSwArr) ))"> {{item.year}}</dt>-->
      <!--<ul >-->
        <!--<li v-if="item.SSUNRF">  {{item.authorsToString}}"{{item.title}}," Korea Copyright Commission, {{item.month}} {{item.day}}, {{item.year}}. (Registration no. {{item.patents}}) <span v-if="item.SSUNRF">SSUNRF : {{item.SSUNRF}}</span></li>-->
      <!--</ul>-->
    <!--</dl>-->
    <!--<br>-->



  </div>

</template>




<script>
  import userList from "./assets/data/lab-data-fixed.json";



  export default {
    name: "userList",
    data() {
      return {
        isWeighted: false,
        isPatent : false,
        isVisible : true,
        isPatentVisible : false,
        isSW : false,
        showMain : true,
        NRFVisible : false,
        ITRCVisible : false,
        IITPVisible : false,
        nrfArr : [],  //nrf 과제
        itrcArr : [], //itrc 과제
        iitpArr : [], //iitp 과제
        sciArr : [],  //sci 저널
        icfArr : [],  //국제 학회
        wsArr : [],  //국제 워크샵
        kciArr : [], //Domestic Journal Articles
        kcfArr : [], //Domestic Conference Proceedings
        krIssPatentArr : [], //국내특허등록
        usPatentArr : [], //미국특허등록
        pctPatentArr : [], //pct 특허 출원
        swArr : [], //소프트웨어 등록
        buttons: [
          { caption: 'Toggle 1', state: true },
          { caption: 'Toggle 2', state: false },

          ]
        }
     },
    watch : {
      isPatent : function() {
        if (this.isPatent) {
          this.isVisible = false;
          this.isPatentVisible = true;
          this.isWeigted = false;
        }else{
          this.isVisible = true;
        }
       // console.log("isVisible : " + this.isVisible )
      },
      isWeighted : function() {
        if (this.isWeighted) {
          this.isPatentVisible = false;
          this.isVisible = true;
          this.isPatent = false;
        }else{

          this.isPatent = false;

        }
        //console.log("isPatentVisible :  " + this.isPatentVisible )
      },


    },
    computed: {
      users() { // #1
        return userList.users.map((items) => { // #2
          // #3


          let authors = [];
          let authorsToString ="";
          let s = "author";
          let temp = ", ";
          let i = 1;
          while(i<25) {
             s = s +i;
//            console.log(s)
            if (items[s] != null ){
              authors.push(items[s])

            }else{
             // console.log(authors)
              for(let j=0; j<authors.length; j++) {
                authorsToString += (authors[j] + temp)
              }
              break
            }
            i++
            s = "author"
          }
          items["authors"] =authors
          items["authorsToString"] = authorsToString

          return items;
        })
      },


      makeNrfArr() {
        return userList.users.map((items) => {

            if (items["SSUNRF"]) {  //nrf 친구들 저장

              this.nrfArr.push(items);
            }


          return this.nrfArr;
        })
      },

      makeItrcArr() {
        return userList.users.map((items) => {


          if (items["SSUITRC"]) {

            this.itrcArr.push(items);
          }

          return this.itrcArr;
        })
      },

      makeIitpArr() {
        return userList.users.map((items) => {


          if (items["EWHAIITP"]) {

            this.iitpArr.push(items);
          }

          return this.iitpArr;
        })
      },
      makeSciArr() {
        return userList.users.map((items) => {


          if (items["type"]==="SCI") {
            this.sciArr.push(items);
          }

          return this.sciArr;
        })
      },

      makeIcfArr() {
        return userList.users.map((items) => {

          if (items["type"]==="국제학회") {
            this.icfArr.push(items);
          }

          return this.icfArr;
        })
      },

      makeWsArr() {
        return userList.users.map((items) => {


          if (items["type"]==="workshop-paper") {
            this.wsArr.push(items);
          }

          return this.wsArr;
        })
      },

      makeKciArr() {
        return userList.users.map((items) => {


          if (items["type"]==="국내저널") {

            this.kciArr.push(items);
          }

          return this.kciArr;
        })
      },

      makeKcfArr() {
        return userList.users.map((items) => {


          if (items["type"]==="국내학회") {

            this.kcfArr.push(items);
          }

          return this.kcfArr;
        })
      },

      makeKrIssPatentArr() {
        return userList.users.map((items) => {


          if (items["type"]==="국내특허등록") {

            this.krIssPatentArr.push(items);
          }

          return this.krIssPatentArr;
        })
      },

      makeUsPatentArr() {
        return userList.users.map((items) => {


          if (items["type"]==="미국특허등록") {

            this.usPatentArr.push(items);
          }

          return this.usPatentArr;
        })
      },

      makePctPatentArr() {
        return userList.users.map((items) => {


          if (items["type"]==="PCT출원") {

            this.pctPatentArr.push(items);
          }

          return this.pctPatentArr;
        })
      },

      makeSwArr() {
        return userList.users.map((items) => {

          if (items["type"]==="SW") {
            this.swArr.push(items);
          }

          return this.swArr;
        })
      },


    },
    methods : {

      yearCalc(index, length, object) {

        let nrfTempYear = 0;
        let obj = object;

//        let obj = this.makeNrfArr;
        let flag = true;


        if(index ===0){
          return true
        }else if(index >= 1){

                 // console.log(`index : ${index}, length : ${length}`)

          if (obj[0][index]["year"] !== obj[0][index-1]["year"]){
              flag = true;
             }else {
            flag = false;
          }


        }
        return flag;
      },

      yearChangeDetect(index, object) {

        let obj = object;

        let flag = true;


        if(index ===0){
          return true
        }else if(index >= 1){

          // console.log(`index : ${index}, length : ${length}`)

          if (obj[index]["year"] !== obj[index-1]["year"]){
            flag = true;
          }else {
            flag = false;
          }


        }
        return flag;
      },

      sortByDate(object){


        let obj = object;
        let originObj = obj;


        obj = obj[0];
        let tempArr = [];
        let sortedObj = [];



        for(let i = 0; i < obj.length; i++){
          let tempObj = {};
          let tempYear = 0;
          let tempMonth = 0;
          let tempDay = 0;
           tempYear = 365*obj[i].year;

             tempMonth = 30 * Number(this.monthConverter(obj[i].month));
          if(obj[i].day){
             tempDay = obj[i].day;
          }
          let dateValueSum = Number(tempYear) + Number(tempMonth) + Number(tempDay);

          tempObj.index = i;
          tempObj.value = dateValueSum;
          tempArr.push(tempObj);

        }

        var sortedByDateArr = tempArr.sort((a,b) => b.value - a.value);

        for(let j = 0 ; j < obj.length ; j++){
          sortedObj.push(originObj[0][sortedByDateArr[j].index] );

        }

        return sortedObj;


      },

      monthConverter(str){
        switch(str){
          case  "January" :
            return 1
          case  "February" :
            return 2
          case  "March" :
            return 3
          case  "April" :
            return 4
          case  "May" :
            return 5
          case  "June" :
            return 6
          case  "July" :
            return 7
          case  "August" :
            return 8
          case  "September" :
            return 9
          case  "October" :
            return 10
          case  "November" :
            return 11
          case  "December" :
            return 12
          defalut :
            return 0
        }

      }


    }
  };
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
