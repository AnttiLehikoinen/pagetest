---
layout: default
title: API
nav_order: 2
parent: Documentation
has_children: true
has_toc : false
---
## API reference
* *class* : [emdtool](emdtool.html)  **emdtool** Main EMDtool utility class.
## Analysis utilities
 Folder with the following files / classes / subfolders:

* *class* : [Analysis utilities/Equivalent Circuits/InverseGammaCircuit](InverseGammaCircuit.html) **InverseGammaCircuit** methods:
* *class* : [/Equivalent Circuits/SynEquivalentCircuit](SynEquivalentCircuit.html) **SynEquivalentCircuit** methods:
* *class* : [IMEquivalentCircuit](IMEquivalentCircuit.html) **IMEquivalentCircuit** is a class.
* *class* : [/Grids/MTPAinterpolant](MTPAinterpolant.html)  **MTPAinterpolant** Interpolant for post-processing field-weakening
* *class* : [/Grids/NTGrid](NTGrid.html) **NTGrid** methods:
* *class* : [/Grids/NTGridDQ](NTGridDQ.html)  **NTGridDQ** Speed-torque grid from d-q grid data.
* *class* : [/Grids/NTGridNT](NTGridNT.html)  
* *class* : [/Grids/OPsimulator](OPsimulator.html)  **OPsimulator** Class for analysing operating points.
* *class* : [/Grids/SMGridCalculator_DQ](SMGridCalculator_DQ.html)  **SMGridCalculator_DQ** DQ-grid calculator for synchronous machines.
* *class* : [/Grids/SMGridCalculator_NT](SMGridCalculator_NT.html)  **SMGridCalculator_NT** (rpm, T) operating point grid calculator.
* *class* : [/Grids/SMGridCalculator_NTfromDQ](SMGridCalculator_NTfromDQ.html) **SMGridCalculator_NTfromDQ** methods:
* *class* : [MTPAinterpolant](MTPAinterpolant.html)  **MTPAinterpolant** Interpolant for post-processing field-weakening
* *class* : [OPiterator](OPiterator.html)  **OPiterator** Backward compatibility proxy class.
## FE Functionality
 Folder with the following files / classes / subfolders:

* *class* : [Elements](Elements.html)  {
* *class* : [IDfun](IDfun.html) **IDfun** is a class.
* *class* : [Nedelec2D](Nedelec2D.html)  **Nedelec2D** class for 2D Nedelec shape functions.
* *class* : [Nedelec3DPrism](Nedelec3DPrism.html)  Nedelec3D class for 3D Nedelec shape functions.
* *class* : [/Elements and Shape Functions/Nodal Elements/Nodal2D](Nodal2D.html)   **Nodal2D** Lagrange (nodal) shape function in 2D.
* *class* : [Operators](Operators.html)  {
* *class* : [/Matrix Assembly/MagneticsJacobian](MagneticsJacobian.html) **MagneticsJacobian** methods:
* *class* : [/Matrix Assembly/MatrixConstructor](MatrixConstructor.html)  **MatrixConstructor** Constructor for FE matrices.
* *class* : [BoundaryMatrixConstructor](BoundaryMatrixConstructor.html) **BoundaryMatrixConstructor** is a class.
* *class* : [MatrixConstructorBase](MatrixConstructorBase.html) **MatrixConstructorBase** is a class.
* *class* : [MatrixConstructor_nonConforming](MatrixConstructor_nonConforming.html) **MatrixConstructor_nonConforming** is a class.
* *class* : [/Mesh/Boundary](Boundary.html)  **Boundary** Base class for boundaries.
* *class* : [/Mesh/DirichletBoundary](DirichletBoundary.html) **DirichletBoundary** methods:
* *class* : [/Mesh/PeriodicBoundary](PeriodicBoundary.html) **PeriodicBoundary** methods:
* *class* : [/Mesh/Airgap mesh/LinearSlidingAirgap](LinearSlidingAirgap.html)  **LinearSlidingAirgap** Airgap class for sliced AFM models.
* *class* : [/Mesh/Airgap mesh/SlidingAirgap](SlidingAirgap.html)  **SlidingAirgap** Sliding airgap model for radial-flux machines.
* *class* : [/Mesh/Airgap mesh/SlidingAirgapBase](SlidingAirgapBase.html) **SlidingAirgapBase** methods:
* *class* : [Airgap](Airgap.html)  **Airgap** Base class for airgap geometries.
* *class* : [MeshBase](MeshBase.html) **MeshBase** is a class.
* *class* : [MeshView](MeshView.html) **MeshView** is a class.
* *class* : [/Mesh/Meshes_3D/TetMesh](TetMesh.html)  **TetMesh** minimal mesh of 3D tetrahedrons.
* *class* : [ExtrudedPrismMesh](ExtrudedPrismMesh.html)  ExtrudedMachineMesh A base class for a MachineMesh extruded into 3D.
* *class* : [MeshBase3D](MeshBase3D.html)  **MeshBase3D** a base class for a 3D mesh.
* *class* : [Nodal3D](Nodal3D.html) **Nodal3D** is a class.
* *class* : [Nodal3D_UpExtruded](Nodal3D_UpExtruded.html) **Nodal3D_UpExtruded** is a class.
* *class* : [Nodal3D_extruded](Nodal3D_extruded.html) **Nodal3D_extruded** is a class.
* *class* : [PrismMeshBase3D](PrismMeshBase3D.html)  **PrismMeshBase3D** A base class for a 3D mesh with prismatic elements.
* *class* : [/Mesh/Other meshes/SimpleMesh](SimpleMesh.html)  **SimpleMesh** Basic mesh class.
* *class* : [Mesh](Mesh.html)  **Mesh** Class for mesh objects.
* *class* : [RotatedMeshView](RotatedMeshView.html) **RotatedMeshView** is a class.
## Geometry
 Folder with the following files / classes / subfolders:

* *class* : [Geometry/Circle](Circle.html)  **Circle** Helper class for circular surfaces.
* *class* : [Domain](Domain.html)  **Domain** **Domain** class.
* *class* : [GeoBase](GeoBase.html)  **GeoBase** Base class for geometries.
* *class* : [LaminatedDomain](LaminatedDomain.html)  **LaminatedDomain** Laminated domain.
* *class* : [Surface](Surface.html)  SURFACE Class for representing elementary surfaces.
* *class* : [/ representation/Arc](Arc.html) **Arc** methods:
* *class* : [/ representation/Curve](Curve.html)  CURVE Abstract base class for representing line segments and circle arcs
* *class* : [/ representation/Line](Line.html) **Line** methods:
* *class* : [/ representation/geo](geo.html)  enumeration
* *class* : [/ representation/gw](gw.html) **gw** methods:
* *class* : [Point](Point.html)  POINT Class for representing points in a geometry.
* *class* : [/Motor geometries/AxialGeometry](AxialGeometry.html) **AxialGeometry** methods:
* *class* : [/Motor geometries/RadialGeometry](RadialGeometry.html)  **RadialGeometry** Base class for radial geometries.
## Materials
 Folder with the following files / classes / subfolders:

* *class* : [Materials/Material](Material.html)  **Material** Basic isotropic material class.
* *class* : [MaterialBase](MaterialBase.html)  **MaterialBase** Base class for materials.
* *class* : [/Hysteretic materials, WIP/HysteresisModel](HysteresisModel.html)  **HysteresisModel** Base class for hysteresis models.
* *class* : [/Hysteretic materials, WIP/HystereticMaterial](HystereticMaterial.html)  **HystereticMaterial** Material class for hysteretic materials.
* *class* : [/Hysteretic materials, WIP/HysteronModel](HysteronModel.html)  **HysteronModel** Base class for vector hysteron models
* *class* : [/Hysteretic materials, WIP/PlayModel](PlayModel.html)  **PlayModel** Play hysteron model.
* *class* : [/Hysteretic materials, WIP/StopModel](StopModel.html)  **StopModel** Hysteresis model based on Stop hysteron.
* *class* : [MaterialSet](MaterialSet.html)  **MaterialSet** Container class.
* *class* : [//SteelLibrary](SteelLibrary.html)  **SteelLibrary** Static class for creating electrical steel Material
* *class* : [Arnon7](Arnon7.html)  **Arnon7** **Arnon7** Material object.
* *class* : [PMlibrary](PMlibrary.html)  **PMlibrary** Static class for creating permanent-magnet Material objects.
* *class* : [deprecated_Vacodur49](deprecated_Vacodur49.html)  Vacodur49 Vacodur49 Material object.
## Problems
 Folder with the following files / classes / subfolders:

* *class* : [Problems/Magnetics/MagneticsProblem](MagneticsProblem.html)  **MagneticsProblem** Class for solving magnetics problems.
* *class* : [HarmonicSolution](HarmonicSolution.html) **HarmonicSolution** is a class.
* *class* : [MagneticsSolution](MagneticsSolution.html)  **MagneticsSolution** Class for representing the solution to MagneticsProblem.
* *class* : [SimulationParameters](SimulationParameters.html)  **SimulationParameters** Parameters for MagneticsProblem solutions.
* *class* : [StaticSolution](StaticSolution.html) **StaticSolution** is a class.
* *class* : [SteppingSolution](SteppingSolution.html) **SteppingSolution** is a class.
## Templates
 Folder with the following files / classes / subfolders:

* *class* : [Templates/AFmodel](AFmodel.html)  only types given?
* *class* : [LinearGeoBase](LinearGeoBase.html) **LinearGeoBase** methods:
* *class* : [RFmodel](RFmodel.html)  **RFmodel** Simple class for radial-flux machines.
* *class* : [/Rotors/BreadloafRotor](BreadloafRotor.html) **BreadloafRotor** methods:
* *class* : [/Rotors/CoatedRotor](CoatedRotor.html) **CoatedRotor** methods:
* *class* : [/Rotors/FWRotor1](FWRotor1.html) **FWRotor1** methods:
* *class* : [/Rotors/HSIPM1](HSIPM1.html) **HSIPM1** methods:
* *class* : [/Rotors/HSIPM2](HSIPM2.html) **HSIPM2** methods:
* *class* : [/Rotors/LinearSPM](LinearSPM.html) **LinearSPM** methods:
* *class* : [/Rotors/MassivePM](MassivePM.html) **MassivePM** methods:
* *class* : [/Rotors/PoledIPM1](PoledIPM1.html) **PoledIPM1** methods:
* *class* : [/Rotors/SPM1](SPM1.html)  **SPM1** Template for a surface-PM rotor.
* *class* : [SPM1](SPM1.html)  **SPM1** Template for a surface-PM rotor.
* *class* : [/Rotors/SRMRotor1](SRMRotor1.html) **SRMRotor1** methods:
* *class* : [/Rotors/ShieldedSPM](ShieldedSPM.html) **ShieldedSPM** methods:
* *class* : [/Rotors/SlottedRotor1](SlottedRotor1.html) **SlottedRotor1** methods:
* *class* : [/Rotors/SpokeRotor1](SpokeRotor1.html)  default dimensions
* *class* : [/Rotors/VIPM1](VIPM1.html)  **VIPM1** V-shape IPM rotor.
* *class* : [SlottedRotorBase](SlottedRotorBase.html)  **SlottedRotorBase** Base class for slotted radial-flux rotors.
* *class* : [SynRotorBase](SynRotorBase.html)  **SynRotorBase** Base class for synchronous machine rotors.
* *class* : [/Slots/CooledSlot1](CooledSlot1.html) **CooledSlot1** methods:
* *class* : [/Slots/Slot1](Slot1.html)  **Slot1** Basic stator slot shape.
* *class* : [/Slots/SlotShapeBase](SlotShapeBase.html)  **SlotShapeBase** Base class for slot shapes.
* *class* : [SlotShapeWrapper](SlotShapeWrapper.html) **SlotShapeWrapper** is a class.
* *class* : [/Stators/FormWound1](FormWound1.html) **FormWound1** methods:
* *class* : [/Stators/LinearStator](LinearStator.html) **LinearStator** methods:
* *class* : [/Stators/OutrunnerFrame](OutrunnerFrame.html) **OutrunnerFrame** methods:
* *class* : [/Stators/PCBStator](PCBStator.html) **PCBStator** methods:
* *class* : [/Stators/SlotlessStator](SlotlessStator.html)  Stator General-purpose stator class for slotted stators.
* *class* : [/Stators/Standard](Standard.html) **Standard** methods:
* *class* : [/Stators/Stator](Stator.html)  **Stator** General-purpose stator class for symmetric slotted stators.
* *class* : [/Stators/StatorBase](StatorBase.html)  **StatorBase** Base class for radial-flux stators.
* *class* : [/Stators/YASAStator](YASAStator.html)  **YASAStator** Axial yokeless stator.
## Third-party
* *class* : [DXFtool](DXFtool.html)   **DXFtool** v1.0 for reading and plotting DXF files in Matlab figures.
## Windings and Circuits
* *class* : [/Circuit Analysis/CircuitGraph](CircuitGraph.html) **CircuitGraph** methods:
* *class* : [/Circuit Analysis/ConcentratedWindingSpec](ConcentratedWindingSpec.html) **ConcentratedWindingSpec** methods:
* *class* : [/Circuit Analysis/DistributedWindingSpec](DistributedWindingSpec.html)  **DistributedWindingSpec** Winding specification class for distributed
* *class* : [/Circuit Analysis/FieldWindingSpec](FieldWindingSpec.html) **FieldWindingSpec** methods:
* *class* : [/Circuit Analysis/PolyphaseWindingSpec](PolyphaseWindingSpec.html)  **PolyphaseWindingSpec** Winding specification class.
* *class* : [/Circuit Analysis/SpaceVectors](SpaceVectors.html)  **SpaceVectors** Class for handling generalized Park-Clarke and inverse
* *class* : [/Circuit Analysis/WindingLayout](WindingLayout.html)  **WindingLayout** Factory class for winding layout matrices.
* *class* : [ParkClarke](ParkClarke.html)  **ParkClarke** Legacy compatibility class.
* *class* : [/FE Circuits/CageCircuit](CageCircuit.html) **CageCircuit** methods:
* *class* : [/FE Circuits/Circuit](Circuit.html)  **Circuit** Simple base class for circuits modelled with the AVI
* *class* : [/FE Circuits/ExtrudedBlockCircuit](ExtrudedBlockCircuit.html) **ExtrudedBlockCircuit** methods:
* *class* : [/FE Circuits/LaminatedCircuit](LaminatedCircuit.html)  **LaminatedCircuit** Class for modelling classical eddy currents in
* *class* : [/FE Circuits/PolyphaseCircuit](PolyphaseCircuit.html)  **PolyphaseCircuit** Class for finite-element representation of polyphase
* *class* : [BlockCircuit](BlockCircuit.html) **BlockCircuit** is a class.
* *class* : [CircuitBase](CircuitBase.html)  **CircuitBase** Abstract base class for finite-element Circuits.
* *class* : [CircuitSet](CircuitSet.html)  **CircuitSet** Class for handling operations on several circuits.
* *class* : [Circuits](Circuits.html) **Circuits** is a class.
* *class* : [/FE Circuits/Conductors/SolidConductor](SolidConductor.html) **SolidConductor** methods:
* *class* : [/FE Circuits/Conductors/SplitConductor](SplitConductor.html) **SplitConductor** methods:
* *class* : [/FE Circuits/Conductors/StrandedConductor](StrandedConductor.html) **StrandedConductor** methods:
* *class* : [Conductor](Conductor.html)  **Conductor** Base class for conductors.
* *class* : [SheetCircuit](SheetCircuit.html) **SheetCircuit** is a class.
* *class* : [/FE Circuits/Sources/VoltageSource](VoltageSource.html)  **VoltageSource** Voltage source class for MagneticsProblem.
* *class* : [/Modulators/SVPWM_Modulator](SVPWM_Modulator.html)  **SVPWM_Modulator** Basic Modulator.
* *class* : [/Modulators/SinusoidalModulator](SinusoidalModulator.html)  **SinusoidalModulator** Sinusoidal voltage modulator.
* *class* : [/Modulators/SpaceVectorModulator](SpaceVectorModulator.html)  **SpaceVectorModulator** Prototype multiphase space vector modulator.
* *class* : [Modulator](Modulator.html)  Base class for modulators.
* *class* : [/Winding layouts/HairpinLayout](HairpinLayout.html) **HairpinLayout** methods:
* *class* : [/Winding layouts/HollowConductorLayout](HollowConductorLayout.html) **HollowConductorLayout** methods:
* *class* : [/Winding layouts/RectangularLayout](RectangularLayout.html) **RectangularLayout** methods:
* *class* : [/Winding layouts/RoundWireLayout](RoundWireLayout.html)  **RoundWireLayout** Winding layout class for random-wound coils.
* *class* : [/Winding layouts/UniformLayout](UniformLayout.html)  **UniformLayout** Layout specification for non-specified layouts:
* *class* : [/Winding layouts/WindingLayoutBase](WindingLayoutBase.html)  **WindingLayoutBase** Base class for winding layouts.
## 
 Folder with the following files / classes / subfolders:

* *class* : [defs](defs.html) **defs** is a class.
* *class* : [emdconstants](emdconstants.html) **emdconstants** is a class.
## to_be_relocated
 Folder with the following files / classes / subfolders:

* *class* : [to_be_relocated/AFmodel2](AFmodel2.html) **AFmodel2** methods:
* *class* : [AirgapContainer](AirgapContainer.html)  **AirgapContainer** Container class for one or more airgap models.
* *class* : [GeoHelper](GeoHelper.html) **GeoHelper** methods:
* *class* : [GeoParser](GeoParser.html) **GeoParser** methods:
* *class* : [GeometryReplicator](GeometryReplicator.html) **GeometryReplicator** methods:
* *class* : [MotorModelBase](MotorModelBase.html)  **MotorModelBase** Base class for magnetics models.
* *class* : [RFmodel2](RFmodel2.html) **RFmodel2** methods:
* *class* : [dxfreader](dxfreader.html) **dxfreader** methods:
* *class* : [/Geometry3D/EdgeBoundaryMatrix](EdgeBoundaryMatrix.html) **EdgeBoundaryMatrix** methods:
* *class* : [/Geometry3D/LinearAVSolver](LinearAVSolver.html) **LinearAVSolver** methods:
* *class* : [/Geometry3D/NodalBoundaryMatrix](NodalBoundaryMatrix.html) **NodalBoundaryMatrix** methods:
* *class* : [/Geometry3D/OctTree](OctTree.html) **OctTree** methods:
* *class* : [/Geometry3D/PointData](PointData.html) **PointData** methods:
* *class* : [/Geometry3D/gw3D](gw3D.html) **gw3D** methods:
* *class* : [/Geometry3D/Geometry extrusion/AxialGeometryExtruder](AxialGeometryExtruder.html) **AxialGeometryExtruder** methods:
* *class* : [/Geometry3D/Geometry extrusion/GeometryExtruder](GeometryExtruder.html) **GeometryExtruder** methods:
* *class* : [/Geometry3D/Geometry extrusion/GlueDomain](GlueDomain.html) **GlueDomain** methods:
* *class* : [/Geometry3D/Geometry extrusion/RadialGeometryExtruder](RadialGeometryExtruder.html) **RadialGeometryExtruder** methods:
* *class* : [Nedelec3D](Nedelec3D.html)  **Nedelec3D** class for 3D Nedelec shape functions.
* *class* : [/Geometry3D/Objects_3D/eCurve](eCurve.html) **eCurve** methods:
* *class* : [/Geometry3D/Objects_3D/eObject](eObject.html) **eObject** methods:
* *class* : [/Geometry3D/Objects_3D/ePoint](ePoint.html) **ePoint** methods:
* *class* : [/Geometry3D/Objects_3D/eSurface](eSurface.html) **eSurface** methods:
* *class* : [/Geometry3D/Objects_3D/eVolume](eVolume.html) **eVolume** methods:
* *class* : [/Mechanical analysis/MechMesh](MechMesh.html) **MechMesh** methods:
* *class* : [/Mechanical analysis/MechUtil](MechUtil.html) **MechUtil** methods:
* *class* : [/Mechanical analysis/ShellEdge](ShellEdge.html) **ShellEdge** methods:
* *class* : [Nodal2D_Quad](Nodal2D_Quad.html) **Nodal2D_Quad** is a class.
* *class* : [NodalBase](NodalBase.html) **NodalBase** is a class.
* *class* : [Quad](Quad.html) **Quad** - (Not recommended) Numerically evaluate integral, adaptive Simpson quadrature
* *class* : [SimpleMesh2](SimpleMesh2.html) **SimpleMesh2** is a class.
## utilities
 Miscellaneous utilities classes and functions.

* *class* : [HashMap](HashMap.html) **HashMap** is a class.
* *class* : [Indexable](Indexable.html) **Indexable** is a class.
* *class* : [SLContainer](SLContainer.html)  **SLContainer** A SMEKlib container class for key-value pairs.
