<template>
  <div class="home">
  <h1>OpenGuitar</h1>
OpenGuitar is a project with focus on STEM education (science,
technology, engineering and math) for children and teenagers from
disadvantaged backgrounds. 

<h3>About Open Guitar</h3>
The ‘OpenGuitar’ is an experimental guitar that can be assembled in
small workshops. The instrument building process is designed as an
engaging and creative activity, which teaches a broad spectrum of
skills, from 3D design and hands-on woodworking to computer aided
manufacturing (CAM), sensor robotics and computer programming with a
focus on the elemental math behind digital signal processing.

<h3>How does the OpenGuitar work?</h3>
The core concept underlying the OpenGuitar is that, although it can
function as a normal piezo driven nylon-string guitar, to obtain the
best sound, it needs to be plugged into a computer. The OpenGuitar is
equipped with an electronic pickup system that allows the connection
with specialised computer software, which in turn enables a broad
spectrum of sound and music making capabilities. Consequently, while
children engage in musical explorations they learn basic skills in
computer programming through step-by-step music computing tutorials. 

<Ramp />

  </div>
</template>

<script>
// @ is an alias to /src
//import OpenGuitar from '@/components/OpenGuitar.vue'
import Ramp from '@/components/Ramp.vue'

export default {
  name: 'Home',
  components: {
    Ramp
  }
}
</script>
