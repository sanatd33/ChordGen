<h1>ChordGen</h1>
<script lang="ts">
    import { onMount, tick } from "svelte";
    import * as Tone from "tone";
    import Key from "$lib/key.svelte";
    let synthConst : Tone.Sampler;
    let notes : string[] = [];
    let prevNotes : string[] = [];
    onMount(()=> {
        Tone.start();
        synthConst = new Tone.Sampler({
            urls: {
                "C4": "c4.wav",
                "D#4": "ds4.wav",
                "F#4": "fs4.wav",
                "A4": "a4.wav"
            },
            baseUrl: "src/lib/"
        }).toDestination();

        setInterval(() => {
            if (!arraysEqual(notes, prevNotes)) {
                // synthConst.triggerAttack(notes);
                prevNotes = [...notes];
            }
        }, 16);
    })

    function arraysEqual(a : any[], b : any[]) {
        if (a == b) return true;
        if (a == null || b == null) return false;
        if (a.length != b.length) return false;

        for (var i = 0; i < a.length; i++) {
            if (a[i] !== b[i]) return false;
        }
        return true;
    }

</script>
<Key class="white" on:mousedown={()=>{
    synthConst.triggerAttack("C4");
    notes.push("C4");
}} on:mouseup={()=>{
    //synth.triggerRelease();
}}>
</Key>

<Key class="black" on:mousedown={()=>{
    notes.push("C#4");
}} on:mouseup={()=>{
    //synth.triggerRelease();
}}>
</Key>

<Key class="white" on:mousedown={()=>{
    notes.push("D4");
}} on:mouseup={()=>{
    //synth.triggerRelease();
}}>
</Key>

<Key class="black" on:mousedown={()=>{
    notes.push("D#4");
}} on:mouseup={()=>{
    //synth.triggerRelease();
}}>
</Key>

<Key class="white" on:mousedown={()=>{
    notes.push("E4");
}} on:mouseup={()=>{
    //synth.triggerRelease();
}}>
</Key>

<Key class="white" on:mousedown={()=>{
    notes.push("F4");
}} on:mouseup={()=>{
    //synth.triggerRelease();
}}>
</Key>

<Key class="black" on:mousedown={()=>{
    notes.push("F#4");
}} on:mouseup={()=>{
    //synth.triggerRelease();
}}>
</Key>

<Key class="white" on:mousedown={()=>{
    notes.push("G4");
}} on:mouseup={()=>{
    //synth.triggerRelease();
}}>
</Key>

<Key class="black" on:mousedown={()=>{
    notes.push("G#4");
}} on:mouseup={()=>{
    //synth.triggerRelease();
}}>
</Key>

<Key class="white" on:mousedown={()=>{
    notes.push("A4");
}} on:mouseup={()=>{
    //synth.triggerRelease();
}}>
</Key>

<Key class="black" on:mousedown={()=>{
    notes.push("A#4");
}} on:mouseup={()=>{
    //synth.triggerRelease();
}}>
</Key>

<Key class="white" on:mousedown={()=>{
    notes.push("B4");
}} on:mouseup={()=>{
    //synth.triggerRelease();
}}>
</Key>

<Key class="white" on:mousedown={()=>{
    notes.push("C5");
}} on:mouseup={()=>{
    //synth.triggerRelease();
}}>
</Key>

<button on:click={()=>{
    notes = [];
}}>
    Reset
</button>