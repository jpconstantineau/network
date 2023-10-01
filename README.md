# network

``` mermaid
flowchart LR
 
    subgraph SASKTEL
        r2p1[WAN]:::active
        r2p2[ROUTER]:::active
        r2p3[DMZ]:::active
        r2p4[DOWN]
    end

    subgraph ROUTER
     r1p1[DEFAULT]:::active
     r1p2[VLAN]:::active
     r1p3[WAN]:::active
    end
    r2p2 --> r1p3 
    r2p3 --> a16p10
    r1p1 --> a16p12
    r1p2 --> a16p11

    subgraph PANEL16
        a16p1[1-TRUNK-LAG2]:::active
        a16p2[2-TRUNK-LAG2]:::active
        a16p3[3-IOTWIRED-50-homeassistant]:::active
        a16p4[4-IOTWIRED-50]
        a16p5[5-TRUNK]:::active
        a16p6[6-TRUNK]:::active
        a16p7[7-TRUNK]:::active
        a16p8[8-LANWIRED-10]:::down
        a16p9[9-LANWIRED-10]:::active
        a16p10[10-DMZ-80-SASKTEL]:::active
        a16p11[11-TRUNK-ROUTER]:::active
        a16p12[12-DEFAULT-1-ROUTER]:::active
        a16p13[13-DEFAULT-1]:::down
        a16p14[14-TRUNK-LAG1]:::down
        a16p15[15-TRUNK-LAG1]:::down
        a16p16[16-TRUNK-AP]:::active
    end

    subgraph SERVER16
        b16p1[1-TRUNK-LAG1]:::active
        b16p2[2-TRUNK-LAG1]:::active
        b16p3[3-LANWIRED-10]:::active
        b16p4[4-LANWIRED-10]:::active
        b16p5[5-LANWIRED-10]:::down
        b16p6[6-LANWIRED-10]:::down
        b16p7[7-LANWIRED-10]:::down
        b16p8[8-LANWIRED-10]:::active
        b16p9[9-LANWIRED-10]:::active
        b16p10[10-LANWIRED-10]:::active
        b16p11[11-IOTWIRED-50]:::down
        b16p12[12-IOTWIRED-50]:::down
        b16p13[13-IOTWIRED-50]:::active
        b16p14[14-IOTWIRED-50]:::active
        b16p15[15-TRUNK-LAG2]:::down
        b16p16[16-TRUNK-LAG2]:::down
    end

    subgraph PIERRE8
        c8p1[1-TRUNK]:::down
        c8p2[2-DMZ-80]:::down
        c8p3[3-LANWIRED-10]:::active
        c8p4[4-LANWIRED-10]:::down
        c8p5[5-LANWIRED-10]:::active
        c8p6[6-LANWIRED-10]:::down
        c8p7[7-LANWIRED-10]:::down
        c8p8[8-TRUNK]:::active
    end

    subgraph ZWIFT8
        d8p1[1-LANWIRED-10]
        d8p2[2-LANWIRED-10]
        d8p3[3-IOTWIRED-50]
        d8p4[4-LANWAIR-20]
        d8p5[5-LANWAIR-20]
        d8p6[6-IOTWIRED-50]
        d8p7[7-TRUNK]:::down
        d8p8[8-TRUNK]:::active
    end

    subgraph SYLVIE8
        e8p1[1-GUESTWIRED-30]
        e8p2[2-GUESTWIRED-30]
        e8p3[3-IOTWIRED-50]
        e8p4[4-IOTWIRED-50]
        e8p5[5-LANWIRED-10]
        e8p6[6-LANWIRED-10]
        e8p7[7-DMZ-80]
        e8p8[8-TRUNK]:::active
    end


    subgraph AP
        ap1[TRUNK]:::active
    end

    c8p8 --> a16p5
    a16p1 --> b16p1
    a16p2 --> b16p2 
    a16p7 --> d8p8
    e8p8 --> a16p6
    ap1 --> a16p16

classDef active stroke:#0f0
classDef down stroke:#f00


```