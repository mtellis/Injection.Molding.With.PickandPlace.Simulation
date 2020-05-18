# SMFG 386 Project

Spring 2020, California State University of Chico

Project Managers: Marshall Ellis, Reese Culbertson, Ryan Martinez 

### Table of Contents
- 1. Introduction
- 2. Bill of materials
- 3. Cell Design
- 4. Hardware Diagram
- 5. Program Workflow
- 6. CoppeliaSim Code to Run Simulation


## 1. Introduction
This project consists of a robot that picks up a finished injection molded part and transfers the part horizontally to a desired location. In our case, we released the part onto a conveyor belt that would then transfer the part into a parts bin. The goal of this project was to use what we had learned in class and replicate how we would potentially use the Plastic’s Lab robot in the injection molding process. Since our group works in the Plastics lab, we were able to apply our knowledge of injection molding and the pick and place process to be able to virtually simulate this scenario. For this project we used CoppeliaSim and Solidworks to design and build both the injection molder and the gantry robot. We then used various joints and knowledge we obtained from working on Lab 1’s Crane example, to be able to apply a non-threaded child script to the scene to be able to simulate and get our projection to function as we hoped. 

## 2. Bill of Materials

![](bompic.png)

----------------------------------------------------------------------------------
## 3. Cell Design

![](Cell_dsign.png)

-----------------------------------------------------------------------------------------------------
## 4. Hardware Diagram

![](hdwr_Diag.png) 

-----------------------------------------------------------------------------------------------------

## 5. Program Workflow Chart

![](Prog_Workflow.png)

--------------------------------------------------

## 6. CoppeliaSim Code to Run Simulation

![](Gifofsim.gif)

function sysCall_init()

    y=sim.getObjectHandle('y_joint')
    hoist=sim.getObjectHandle('HoistActuator')
    succ=sim.getScriptHandle('suctionPad')
    
    
    xml = [[
<ui title="speed control" closeable="true" resizable="false" activate="false">
    <group layout="form" flat="true">
        <label text="y speed (m/s): 0.00" id="3"/>
        <hslider tick-position="above" tick-interval="1" minimum="-5" maximum="5" on-change="actuatey" id="2"/>
        <label text="hoist speed (m/s): 0.00" id="1"/>
        <hslider tick-position="above" tick-interval="1" minimum="-5" maximum="5" on-change="actuatehoist" id="4"/>
        <label text="Magnet" id="5"/>
        <button text="deactivate" on-click="actuateMagnet" checkable="true" id="6"/>
    </group>
    <label text="" style="* {margin-left: 400px;}"/>
</ui>
]]
        ui=simUI.create(xml)
end
function actuatehoist(ui,id,newVal)
 local val = 0.25*newVal
    sim.setJointTargetVelocity(hoist,val)
    simUI.setLabelText(ui,1,string.format("hoist speed (m/s): %.2f",val))
end
function actuatey(ui,id,newVal)
 local val = 0.15*newVal
    sim.setJointTargetVelocity(y,val)
    simUI.setLabelText(ui,3,string.format("y speed (m/s): %.2f",val))
end
function actuateMagnet(ui)
    local state = sim.getScriptSimulationParameter(succ,'active')
    if state then
        sim.setScriptSimulationParameter(succ,'active','false')
        simUI.setButtonText(ui,5,"deactivated")
    else
        sim.setScriptSimulationParameter(succ,'active','true')
        simUI.setButtonText(ui,5,"activated")
    end
end
