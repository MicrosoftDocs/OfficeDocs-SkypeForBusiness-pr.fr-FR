---
title: "Lync Server 2013 : Techn. de virtualis. prises en charge et limites connues"
TOCTitle: Technologies de virtualisation prises en charge et limites connues
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204982(v=OCS.15)
ms:contentKeyID: 49297532
ms.date: 02/06/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Technologies de virtualisation prises en charge et limites connues dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2017-02-06_

Le plug-in VDI de Lync permet les appels audio et vidéo pour les technologies de virtualisation prises en charge. Cela permet d’étendre la fonctionnalité indiquée pour Microsoft Lync Server 2010 dans le livre blanc [Client Virtualization in Microsoft Lync 2010](http://go.microsoft.com/fwlink/?linkid=330447). Conformément aux réglementations téléphoniques standard, la prise en charge pour E911 est également incluse. Les sections suivantes décrivent les technologies de virtualisation prises en charge par le plug-in VDI de Lync et les limitations connues.

## Prise en charge des technologies de virtualisation

Le plug-in VDI de Lync prend en charge l’accès à distance au bureau complet dans le scénario de bureau virtuel personnel, mais pas dans le scénario de session de bureau à distance. Ces scénarios peuvent être décrits comme suit :

  - **Pris en charge : bureaux virtuels personnalisés ou VDI (Virtual Desktop Infrastructure).**   Dans ce scénario, chaque utilisateur se connecte à un bureau virtuel personnalisable et peut enregistrer sur le bureau des fichiers qui seront conservés au cours des différentes sessions. Les services Bureau à distance de Microsoft, VMware Horizon View et Citrix XenDesktop sont des implémentations testées avec Lync. Pour plus d’informations sur les environnements VDI propres aux fournisseurs et le matériel client testés par Microsoft, reportez-vous à [Infrastructure qualified for Microsoft Lync (Infrastructure agréée pour Microsoft Lync)](http://go.microsoft.com/fwlink/?linkid=313435).

  - **Non pris en charge : sessions de bureau à distance.**   Dans ce scénario, chaque utilisateur se connecte à une session de bureau virtuel générique qui ne peut pas être personnalisée. Les exemples d’implémentations incluent les sessions Bureau à distance de Microsoft (RDSH) et Citrix XenApp combiné à Citrix Receiver.

Le plug-in VDI de Lync ne prend pas en charge les autres technologies de virtualisation, telles que la virtualisation d’application, qui permet l’utilisation d’une application sans avoir à installer localement l’application complète. Les exemples d’implémentations incluent Citrix XenApp et Microsoft Application Virtualization (App-V). Les modes de diffusion en continu d’application, de mise à distance d’application et de virtualisation mixte (par exemple, mise à distance d’application dans une mise à distance de bureau complet) ne sont pas pris en charge.

Pour permettre l’extensibilité, le plug-in VDI de Lync a été conçu pour utiliser les API indépendantes des plateformes appelées Canaux virtuels dynamiques (DVC). Pour les scénarios qui ne sont pas explicitement pris en charge par Lync, reportez-vous à l’assistance du fournisseur de solution VDI.

## Limitations de fonctionnalité connues

Les limites connues à l’utilisation de Lync 2013 dans un environnement VDI sont les suivantes :

  - La prise en charge des fonctionnalités de délégation d’appel et d’anonymisation des agents Response Group est limitée.

  - Il n’existe pas de prise en charge pour les fonctionnalités suivantes :
    
      - pages de réglage des périphériques audio et vidéo intégrés ;
    
      - vidéo à vues multiples ;
    
      - enregistrement des conversations ;
    
      - participation anonyme à des réunions (c’est-à-dire participation à des réunions Lync hébergées par une organisation qui n’est pas fédérée à la vôtre) ;
    
      - utilisation du plug-in Lync VDI avec un périphérique Lync Phone Edition ;
    
      - continuité des appels en cas de panne du réseau ;
    
      - sonneries personnalisées et fonctionnalités d’attente musicale.

  - Le plug-in VDI de Lync n’est pas pris en charge dans un environnement Office 365.

