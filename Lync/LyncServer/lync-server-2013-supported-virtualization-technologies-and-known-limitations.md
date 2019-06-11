---
title: 'Lync Server 2013 : Technologies de virtualisation prises en charge et limites connues'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b5c99151be45f70d1d95fa0a89835ebb6f7d352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Technologies de virtualisation prises en charge et limites connues dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2017-02-06_

Le plug-in Lync VDI autorise les appels audio et vidéo pour les technologies de virtualisation prises en charge. Cette opération étend les fonctionnalités de Microsoft Lync Server 2010 dans le livre blanc [sur la virtualisation du client dans Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) . Conformément aux réglementations téléphoniques standard, la prise en charge pour E911 est également incluse. Les sections suivantes décrivent les technologies de virtualisation prises en charge par le plug-in Lync VDI et les limitations de fonctionnalités connues.

<div>

## <a name="support-for-virtualization-technologies"></a>Prise en charge des technologies de virtualisation

Le plug-in Lync VDI prend en charge l’accès complet au bureau virtuel dans le scénario de bureau virtuel personnel, mais pas dans le scénario de session Bureau à distance. Ces scénarios peuvent être décrits comme suit :

  - **Pris en charge: les bureaux virtuels personnalisés ou l’infrastructure de bureau virtuelle.**    Dans ce scénario, chaque utilisateur se connecte à un bureau virtuel personnalisable et est en mesure d’enregistrer des fichiers sur le bureau qui persistent dans toutes les sessions. Les services Bureau à distance de Microsoft, le mode d’affichage horizontal de VMware et Citrix XenDesktop sont des implémentations qui ont été testées pour Lync. Pour plus d’informations sur les environnements VDI spécifiques aux fournisseurs et sur le matériel client testés par Microsoft, voir [infrastructure Qualified pour Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).

  - **Non pris en charge: sessions de bureau à distance.**    Dans ce scénario, chaque utilisateur se connecte à une session de bureau virtuel générique qui ne peut pas être personnalisée. Les exemples d’implémentations incluent les sessions Bureau à distance de Microsoft (RDSH) et Citrix XenApp combiné à Citrix Receiver.

Le plug-in Lync VDI ne prend pas en charge les autres technologies de virtualisation, telles que la virtualisation de l’application, qui permet d’utiliser une application sans avoir besoin d’installer entièrement l’application en local. Les exemples d’implémentations incluent Citrix XenApp et Microsoft Application Virtualization (App-V). Les modes de diffusion en continu d’application, de mise à distance d’application et de virtualisation mixte (par exemple, mise à distance d’application dans une mise à distance de bureau complet) ne sont pas pris en charge.

Pour autoriser l’extensibilité, le plug-in Lync VDI a été conçu pour utiliser des API indépendantes de la plateforme appelées canaux virtuels dynamiques (DVCs). Dans le cas de scénarios non pris en charge de manière explicite par Lync, voir instructions d’assistance du fournisseur de solutions VDI.

</div>

<div>

## <a name="known-feature-limitations"></a>Limitations de fonctionnalité connues

Vous trouverez ci-après des limitations connues lorsque vous utilisez Lync 2013 dans un environnement VDI:

  - La prise en charge des fonctionnalités de délégation d’appel et d’anonymisation de l’agent de Response Group est limitée.

  - Il n’existe pas de prise en charge pour les fonctionnalités suivantes :
    
      - pages de réglage des périphériques audio et vidéo intégrés ;
    
      - vidéo à vues multiples ;
    
      - enregistrement des conversations ;
    
      - Services Bureau à distance.
    
      - La participation anonyme aux réunions (c’est-à-dire, la participation à des réunions Lync hébergées par une organisation non fédérée avec votre organisation).
    
      - Utiliser le plug-in Lync VDI avec un appareil Lync Phone Edition.
    
      - continuité des appels en cas de panne du réseau ;
    
      - sonneries personnalisées et fonctionnalités d’attente musicale.

  - Le plug-in Lync VDI n’est pas pris en charge dans un environnement Office 365.

</div>

</div>

<span> </span>

</div>

</div>

</div>

