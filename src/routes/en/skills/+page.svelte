<script>
	import { onMount } from "svelte";
    import Box from "../../../Components/Box.svelte";
    import Ellipse from "../../../Components/Ellipse.svelte";
    import Buttons from "../../../Components/Buttons.svelte";
    import CircleStar from "../../../Components/circleStar.svelte";
    

    let skillBox, skillW, skillH, languagesBox, langH, langW, learningBox, learnW, learnH, windowWidth, sizeBracket1=185, sizeBracket2=150;
    onMount(()=>{
        // windowWidth = window.innerWidth;
        skillBox = document.getElementById("skills");
        languagesBox = document.getElementById("languages");
        learningBox = document.getElementById("learning");
        windowWidth = window.innerWidth;

    })

    // $:if(windowWidth){if (windowWidth>600) {skillW = 368; skillH=328}
    //     else if (windowWidth<600) {skillW = 140; skillH=110}
    //     else if (windowWidth<365) {skillW = 90; skillH=50}}
    $:if(skillBox) skillW = skillBox.clientWidth + 20
    $:if(skillBox) skillH = skillBox.clientHeight + 20
    $:if(languagesBox) langW = languagesBox.clientWidth + 20
    $:if(languagesBox) langH = languagesBox.clientHeight + 20
    $:if(learningBox) learnW = learningBox.clientWidth + 20
    $:if(learningBox) learnH = learningBox.clientHeight + 20

    $:if (windowWidth>600) {sizeBracket1 = 185; sizeBracket2=150}
        else if (windowWidth<600) {sizeBracket1 = 140; sizeBracket2=110}
        else if (windowWidth<365) {sizeBracket1 = 90; sizeBracket2=50}
</script>

<div class="flex justify-center items-center lg:gap-4 xl:mx-0 lg:mt-20 mt-2 gap-2 xxs:gap-2 xs:mx-5 xxs:mx-4 xxs:mt-4 s-688:flex-col s-688:mx-10 xxs:mx-14 2xl:justify-around 2xl:mx-52 2xl:mt-20 mainSkillContent">
   
    <div class="h-full flex flex-col justify-center items-center lg:w-2/5 xl:w-2/5 s-688:w-11/12">
        <h1 class="h3 mb-4 text-green-700 text-3xl xs:text-lg xxs:text-sm">Skills</h1>
        <div class="relative w-full h-full flex-col justify-center items-center" id="skills">
            <div class="w-full h-full flex flex-col justify-center items-center">
                <h1 class="h3 xl:text-3xl text-xl xs:text-sm xxs:text-xs"><span class="text-blue-700">Python</span>, PYQT5, FastAPI, Flask</h1>
                <h1 class="h3 xl:text-3xl text-xl xs:text-sm xxs:text-xs"><span class="text-blue-700">Tensorflow</span>, <span class="text-blue-700">Pytorch</span></h1>
                <h1 class="h3 xl:text-3xl text-xl xs:text-sm xxs:text-xs">Data (Analysis) Preprocessing</h1>
                <h1 class="h3 xl:text-3xl text-xl xs:text-sm xxs:text-xs">Machine Learning and Deep Learning</h1>
                <h1 class="h3 xl:text-3xl text-xl xs:text-sm xxs:text-xs"><span class="text-blue-700">Natural Language Processing</span></h1>
                <h1 class="h3 xl:text-3xl text-xl xs:text-sm xxs:text-xs"><span class="text-blue-700">Computer Vision</span></h1>
                <h1 class="h3 xl:text-3xl text-xl xs:text-sm xxs:text-xs"><span class="text-blue-700">Generative adversarial network</span></h1>
                <h1 class="h3 xl:text-3xl text-xl xs:text-sm xxs:text-xs">AI Model Deployment and Integration</h1>
                <h1 class="h3 xl:text-3xl text-xl xs:text-sm xxs:text-xs">HTML, CSS, Scss, Javascript</h1>
                <h1 class="h3 xl:text-3xl text-xl xs:text-sm xxs:text-xs"><span class="text-blue-700">Sveltekit</span>, <span class="text-blue-700">Reactjs</span>, VueJs, Angular2+</h1>
                <h1 class="h3 xl:text-3xl text-xl xs:text-sm xxs:text-xs">MongoDB, Nodejs, React native</h1>
                <h1 class="h3 xl:text-3xl text-xl xs:text-sm xxs:text-xs">Photoshop, Figma</h1>
            </div>

            {#if skillBox}
                <Box boxwidth={skillW} boxheight={skillH} idName={"box-skills"}/>
            {/if}
            
        </div>
    </div>
    <div class="h-full flex flex-col justify-center items-center w-1/4 s-688:w-full mt-4 xxs:mt-4 ">
        <div class="xxs:flex xxs:justify-start xxs:items-start xxs:gap-1 xxs:flex-col">
            <h1 class="h3 mb-8 text-green-700 text-3xl xs:text-lg xxs:text-sm ">Languages</h1>
            <div class="relative w-full" id="languages">
                <h1 class={`h3 flex gap-1 text-xl justify-start items-start xs:text-sm xxs:text-xs ${typeof InstallTrigger !== 'undefined'?"h-7 w-52":""}`}>English <CircleStar idName={"startE"} stars={[1, 1, 1, 1, 1]}/></h1>
                <h1 class={`h3 flex gap-1 text-xl justify-start items-start xs:text-sm xxs:text-xs ${typeof InstallTrigger !== 'undefined'?"h-7 w-52":""}`}>French<CircleStar idName={"startF"} stars={[1, 1, 0, 0, 0]}/></h1>
                <h1 class={`h3 flex gap-1 text-xl justify-start items-start xs:text-sm xxs:text-xs ${typeof InstallTrigger !== 'undefined'?"h-7 w-52":""}`}>Hindi<CircleStar idName={"startH"} stars={[1, 1, 1, 1, 1]}/></h1>
                {#if languagesBox}
                    <Ellipse boxwidth={langW} boxheight={langH} idName={"box-lang"}/>
                {/if}
                
            </div>
        </div>
        <!-- <div class="mt-8 xxs:flex xxs:justify-start xxs:items-start xxs:gap-5 xxs:mt-10">
            <h1 class="h3 mb-4 text-3xl xs:text-lg xxs:text-sm">Learning...</h1>
            <div class="relative w-full h-full flex flex-col justify-center items-center xxs:flex-row xxs:justify-start xxs:items-start xxs:gap-5" id="learning">
                <h1 class="h3 text-xl xs:text-sm xxs:text-xs"><span class="text-green-700">French</span></h1>
                <h1 class="h3 text-xl xs:text-sm xxs:text-xs">Docker</h1>
                <h1 class="h3 text-xl xs:text-sm xxs:text-xs">SQL</h1>
                {#if learningBox}
                    <Box boxwidth={learnW} boxheight={learnH} idName={"box-learn"}/>
                {/if}
                
            </div>
        </div> -->
        
    </div>
    <div  class="h-full flex flex-col justify-center items-center w-1/4 s-688:w-full mt-10 xs:mt-20 xxs:mt-12">
        <Buttons buttonwidth={280} idName={"buttonAnchor2"} buttonName={"I think you want my resume."}/>
    </div>
</div>