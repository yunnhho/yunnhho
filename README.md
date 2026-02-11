## Hi there 👋

<!--
**yunnhho/yunnhho** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

---

```mermaid
graph LR
    subgraph Kernel Space
        LogFile[Log File]
        DockerSock[Docker Socket]
    end

    subgraph "User Space (Off-Heap / Native)"
        DirectBuf[Direct ByteBuffer<br/>(Circular Reuse)]
        Hyperscan[Intel Hyperscan<br/>(JNI Binding)]
        RingBuf[LMAX Disruptor<br/>(16k Slots)]
        RuleEngine[RoaringBitmap<br/>(Logic)]
        ActionBuf[Pre-serialized Cmd<br/>(DirectBuffer)]
    end

    LogFile -- sys_read --> DirectBuf
    DirectBuf -- Pointer Addr --> Hyperscan
    Hyperscan -- Match ID (int) --> RingBuf
    RingBuf -- Event --> RuleEngine
    RuleEngine -- Trigger --> ActionBuf
    ActionBuf -- sys_write --> DockerSock
```
