## Welcome NVIDIA Omniverse™ on GitHub

NVIDIA Omniverse is a collection of accelerated libraries, OpenUSD tooling, and sample repositories for developing Physical AI simulation applications and agentic wokflows, tuned specially for — robotics simulation, industrial digital twins, and synthetic data generation.

These repositories expose Omniverse core technologies as standalone, embeddable libraries with well-defined C and Python APIs. Integrate RTX rendering, PhysX simulation, streaming, and storage directly into your existing applications and training pipelines.

Learn more here: [NVIDIA Omniverse](https://www.nvidia.com/en-us/omniverse/) 

## Physical AI workflows

| Workflow | What you build | Key libraries |
|----------|----------------|---------------|
| **Robotics simulation & training** | RL/IL environments, policy validation, Isaac Lab–style headless physics at scale | [ovphysx](https://github.com/NVIDIA-Omniverse/PhysX/tree/main/ovphysx), [ovrtx](https://github.com/NVIDIA-Omniverse/ovrtx), [ovstream](https://github.com/NVIDIA-Omniverse/ovstream) |
| **Industrial digital twins & VFI** | Factory layouts, operations simulation, PLM-connected asset pipelines | [ovstorage](https://github.com/NVIDIA-Omniverse/ovstorage), [ovpackage](https://github.com/NVIDIA-Omniverse/ovpackage), OpenUSD tooling (below) |
| **Sensor rendering & synthetic data** | Multimodal perception, defect/augmentation datasets, scalable GPU rendering | [ovrtx](https://github.com/NVIDIA-Omniverse/ovrtx), [usd-convert-*](https://github.com/NVIDIA-Omniverse/usd-convert-asset), Physical AI skills (below) |

## Omniverse Libraries

Standalone, embeddable libraries that bring core Omniverse technologies to any application. Each provides C and/or Python APIs, and most ship agent skills for AI-assisted development (see [Agent Skills and MCP Servers](#agent-skills-and-mcp-servers) below).

### Core simulation & data

| Library | Description |
|---------|-------------|
| [ovrtx](https://github.com/NVIDIA-Omniverse/ovrtx) | A C and Python library for physically accurate, real-time sensor simulation and visualization using NVIDIA Omniverse RTX, which also enables headless SDG. |
| [ovphysx](https://github.com/NVIDIA-Omniverse/PhysX/tree/main/ovphysx) | USD physics simulation built on the NVIDIA PhysX SDK — C API with Python bindings, DLPack tensor interop, and environment cloning for batched reinforcement learning. Part of the [PhysX](https://github.com/NVIDIA-Omniverse/PhysX) repository. |
| [ovstorage](https://github.com/NVIDIA-Omniverse/ovstorage) | Agent-first, plugin-based storage client for local files, cloud object stores, and Omniverse Storage services. |

### Application composition

| Library | Description |
|---------|-------------|
| [ovui](https://github.com/NVIDIA-Omniverse/ovui) | The standalone distribution of Omniverse's omni.ui UI framework — a declarative, Python-first API for building hardware-accelerated desktop interfaces backed by ImGui — plus application widget and OpenUSD data-adapter layers. |
| [ovstream](https://github.com/NVIDIA-Omniverse/ovstream) | Stream video, audio, and input over WebRTC, RTSP, native, and shared-memory transports, with GPU-accelerated NVENC encoding for remote teleop and visualization. |
| [ovpackage](https://github.com/NVIDIA-Omniverse/ovpackage) | Reproducible asset packaging and publishing across local and cloud storage backends for SimReady and production pipelines. |

## OpenUSD Tooling and SDKs

OpenUSD is the shared scene description layer across Omniverse libraries, Isaac Sim, and industrial digital-twin pipelines. These repos help you author, validate, convert, optimize, and search USD content for simulation-ready assets:

- [usd-exchange](https://github.com/NVIDIA-Omniverse/usd-exchange) — OpenUSD Exchange SDK for authoring consistent and correct USD ([samples](https://github.com/NVIDIA-Omniverse/usd-exchange-samples))
- [usd-validation-nvidia](https://github.com/NVIDIA-Omniverse/usd-validation-nvidia) — extensible framework to validate OpenUSD assets
- [usd-profiles-nvidia](https://github.com/NVIDIA-Omniverse/usd-profiles-nvidia) — framework for defining and managing OpenUSD asset profiles, capabilities, and requirements
- [usd-optimize](https://github.com/NVIDIA-Omniverse/usd-optimize) — library to optimize OpenUSD stages
- [usd-convert-asset](https://github.com/NVIDIA-Omniverse/usd-convert-asset), [usd-convert-cad](https://github.com/NVIDIA-Omniverse/usd-convert-cad), and [usd-convert-gsplat](https://github.com/NVIDIA-Omniverse/usd-convert-gsplat) — converters for common asset formats, CAD data, and 3D Gaussian Splats
- [usd-search](https://github.com/NVIDIA-Omniverse/usd-search) — cloud-native microservices for searching OpenUSD asset collections by natural language or reference image ([client library](https://github.com/NVIDIA-Omniverse/usdsearch-client))


### Omniverse Labs

[Omniverse Labs](https://github.com/NVIDIA-Omniverse/omniverse-labs) is where you can explore experimental projects and early samples. These repositories are useful for learning, prototyping, and seeing what teams are testing, but they may change faster than supported libraries or documented workflows.

## Agent friendliness

Omniverse is designed to work well with AI coding assistants and agentic development workflows. The key idea is simple: agents are most useful when they can call real tools, inspect scene state, search APIs, apply changes, and return evidence for human review.

## Agent Skills and MCP Servers

Omniverse libraries and Kit expose MCP servers so LLM-based agents can load scenes, step simulation, and generate USD/UI code safely. Per-library agent skills provide on-demand reference for coding assistants.

| Name | Type | Description | Repository |
|------|------|-------------|------------|
| **ovrtx** | Agent Skills | Omniverse RTX SDK — renderer setup, USD scene loading, rendering, attribute writing, CUDA/Vulkan interop, and project scaffolding. | [ovrtx/skills/](https://github.com/NVIDIA-Omniverse/ovrtx/tree/main/skills) |
| **ovphysx** | Agent Skills | USD physics simulation — C API with Python bindings, DLPack tensor interop, environment cloning for batched RL, and rigid body simulation. | [PhysX/ovphysx/](https://github.com/NVIDIA-Omniverse/PhysX/tree/main/ovphysx) |
| **ovui** | Agent Skills | Standalone omni.ui framework — declarative Python UI building, widgets, layout, and styling. | [ovui/skills/](https://github.com/NVIDIA-Omniverse/ovui/tree/main/skills) |
| **ovstream** | Agent Skills | Streaming library — video, audio, and input streaming over WebRTC, RTSP, native, and shared-memory transports. | [ovstream/skills/](https://github.com/NVIDIA-Omniverse/ovstream/tree/main/skills) |
| **ovstorage** | Agent Skills | Storage client — local files, cloud object stores, and Omniverse Storage services. | [ovstorage/skills/](https://github.com/NVIDIA-Omniverse/ovstorage/tree/main/skills) |
| **ovpackage** | Agent Skills | Asset packaging and publishing — CLI and Python API workflows. | [ovpackage/.agents/skills/](https://github.com/NVIDIA-Omniverse/ovpackage/tree/main/.agents/skills) |
| **Kit MCP** | MCP Server | Kit development assistant — semantic search across 400+ extensions, dependency graphs, API docs, code examples, and app templates. | [kit-usd-agents/source/mcp/kit_mcp/](https://github.com/NVIDIA-Omniverse/kit-usd-agents/tree/main/source/mcp/kit_mcp) |
| **USD Code MCP** | MCP Server | USD/OpenUSD development assistant — module and class browsing, method signatures, code examples, and semantic search. | [kit-usd-agents/source/mcp/usd_code_mcp/](https://github.com/NVIDIA-Omniverse/kit-usd-agents/tree/main/source/mcp/usd_code_mcp) |
| **OmniUI MCP** | MCP Server | OmniUI development assistant — class and module browsing, method docs, code examples, and system instructions. | [kit-usd-agents/source/mcp/omni_ui_mcp/](https://github.com/NVIDIA-Omniverse/kit-usd-agents/tree/main/source/mcp/omni_ui_mcp) |

### Physical AI Skills

These skills complement the libraries above for end-to-end Physical AI workflows — CAD-to-SimReady asset prep, neural reconstruction, defect SDG, infrastructure scaling, and USD performance tuning.

- [omniverse-cad-to-simready](https://github.com/NVIDIA/skills/tree/main/skills/omniverse-cad-to-simready)
- [omniverse-realtime-viewer](https://github.com/NVIDIA/skills/tree/main/skills/omniverse-realtime-viewer)
- [omniverse-usd-performance-tuning](https://github.com/NVIDIA/skills/tree/main/skills/omniverse-usd-performance-tuning)
- [physical-ai-defect-image-generation](https://github.com/NVIDIA/skills/tree/main/skills/physical-ai-defect-image-generation)
- [physical-ai-infrastructure-setup-and-resilient-scaling](https://github.com/NVIDIA/skills/tree/main/skills/physical-ai-infrastructure-setup-and-resilient-scaling)
- [physical-ai-neural-reconstruction](https://github.com/NVIDIA/skills/tree/main/skills/physical-ai-neural-reconstruction)
- [physical-ai-video-data-augmentation](https://github.com/NVIDIA/skills/tree/main/skills/physical-ai-video-data-augmentation)

These skills are also available in [Vercel's Skill Marketplace](https://www.skills.sh/nvidia/skills) under the Physical AI section, and as plugins in the Claude Code marketplace and Codex marketplace.

See also the [NVIDIA Agent Skills catalog](https://github.com/NVIDIA/skills) for skills across the NVIDIA ecosystem.

## Blueprints and Workflows
Omniverse Workflows and Blueprints provide step-by-step guides and reference implementations for a variety of development scenarios. They can help you get started quickly with use cases such as robotics training environments, AI-factory digital twins (DSX), synthetic data pipelines, virtual facility integration (VFI), and configurator development. These are built on Omniverse libraries and OpenUSD.

- [Blueprints and Workflows Documentation](https://docs.nvidia.com/omniverse/index.html#blueprints-workflows)
- [NVIDIA-Omniverse-blueprints on GitHub](https://github.com/NVIDIA-Omniverse-blueprints)

## Additional Resources

- [Omniverse Developer Page](https://developer.nvidia.com/omniverse)
- [Omniverse Platform Documentation](https://docs.nvidia.com/omniverse/index.html)
- [LearnOpenUSD](https://github.com/NVIDIA-Omniverse/LearnOpenUSD) and [OpenUSD docs](https://docs.nvidia.com/omniverse/index.html#openusd) |
- [Integrate Physical AI into existing apps (technical blog)](https://developer.nvidia.com/blog/integrate-physical-ai-capabilities-into-existing-apps-with-nvidia-omniverse-libraries/)
- [Isaac Sim](https://developer.nvidia.com/isaac-sim) · [Isaac Lab](https://github.com/isaac-sim/IsaacLab) — robotics simulation frameworks adopting Omniverse libraries
- [NVIDIA Agent Skills catalog](https://github.com/NVIDIA/skills/tree/main/skills)
- [Omniverse Discord](https://discord.com/invite/nvidiaomniverse) — feedback on early-access libraries
- [NVIDIA Omniverse Developer Forums](https://forums.developer.nvidia.com/c/omniverse/300) | - Join in on the discussions at the Omniverse Forums
- Enterprise support | Use your NVIDIA enterprise support channel or contact your NVIDIA representative.
