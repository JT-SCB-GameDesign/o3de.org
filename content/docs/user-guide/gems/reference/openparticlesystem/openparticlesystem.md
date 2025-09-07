## **O3DE Open Particle System Gem**

The OPS is implemented as a standalone Gem. It contains a particle runtime, a particle editor, a particle asset and its builder.

### **Particle Runtime**

The particle system supports 3 types of particles: sprite particle, ribbon particle and mesh particle. Each type of particle supports kinds of velocity, speed and forces. The logic of creating and using the particles are more or less similar to what is in other major AAA engines.

The gem itself has some particle samples, so one can add a particle entity in the level and open a sample particle to take a try.

### **Particle Editor**

The particle editor can create or modify the particles.  It can open multiple particles at one time. Multiple emitters can be added for each particle in it.

Also, the particles are saved as .particle files.  So there is a corresponding particle asset builder.

### **Other Features**

#### **CPU Particle**

Currently, all particle movements are calculated by the CPU.  If large scale particle systems are used, there is a trade off in performance. 

#### **Particle Simulation Core**

The rendering of the particle via the draw calls are sent to a forward/transparent pass to draw them.  It is more or less following the engine's draw procedure and using the engine's infrastructure. Movement update control used to be a separate library but is now in the SimuCore.

**Complex Physical Collision**

Currently, the particle can only have a physical collision with a plane, this is very simple. Colliding with meshes and actors requires some changes in the engine to get the shape and position. Ideally collisions should be possible with meshes, actors, water and terrain.

#### **Particle Logic and Editor Enhancement**

The particle system is flexible enough to use as is but could use the following enhancements to be on par with other engine’s particle systems:

* Support for manual movement track, by manual curve  
* Maximum/minimum values supported by curve  
* Particle events open to the engine  
* Particle support in timeline preview  
* Preview of particle material  
* One-key reset default value  
* Copy-paste of float3 values  
* Auto save of particle documents

#### **Multi-material Support for Particles**

Currently, the mesh particle can only be shaded with standard PBR shading.  Multi-material shading support can be added in the future.

### **Known Issues**

A particle system is actually very complex, so there are still some notable issues.  For example, the storage of the particle curve and random values sometimes might not work properly.  The particle document format can be refactored to be more stable.
