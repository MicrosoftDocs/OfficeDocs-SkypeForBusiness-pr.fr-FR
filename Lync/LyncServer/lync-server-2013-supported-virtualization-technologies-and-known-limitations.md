---
title: 'Lync Server 2013 : technologies de virtualisation prises en charge et limitations connues'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0968f79b8c9aedc3dc2d2318a2e8abf5c51531d7
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Technologies de virtualisation prises en charge et limitations connues dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2017-02-06_

Le plug-in Lync VDI autorise les appels audio et vidéo pour les technologies de virtualisation prises en charge. Cela étend les fonctionnalités décrites pour Microsoft Lync Server 2010 dans le livre blanc sur la [virtualisation des clients dans Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) . Conformément aux réglementations téléphoniques standard, la prise en charge de E911 est également incluse. Les sections suivantes décrivent les technologies de virtualisation prises en charge par le plug-in Lync VDI et les limitations de fonctionnalités connues.

<div>

## <a name="support-for-virtualization-technologies"></a>Prise en charge des technologies de virtualisation

Le plug-in Lync VDI prend en charge l’accès à distance complet au bureau dans le scénario de bureau virtuel personnel, mais pas dans le scénario de session de bureau à distance. Ces scénarios peuvent être décrits comme suit :

  - **Pris en charge : bureaux virtuels personnalisés ou VDI (Virtual Desktop Infrastructure).**     Dans ce scénario, chaque utilisateur se connecte à un bureau virtuel personnalisable et peut enregistrer des fichiers sur le bureau qui persistent dans les sessions. Les services Bureau à distance de Microsoft, l’affichage de l’horizon VMware et Citrix XenDesktop sont des implémentations testées pour une utilisation avec Lync. Pour plus d’informations sur les environnements VDI et le matériel client spécifiques aux fournisseurs qui ont été testés par Microsoft, voir [infrastructure Qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).

  - **Non pris en charge : sessions de bureau à distance.**     Dans ce scénario, chaque utilisateur se connecte à une session de bureau virtuel générique qui ne peut pas être personnalisée. Les exemples d’implémentation incluent les sessions Bureau à distance de Microsoft et Citrix XenApp combinés avec le récepteur Citrix.

Le plug-in Lync VDI ne prend pas en charge les autres technologies de virtualisation, telles que la virtualisation d’application, qui permet l’utilisation d’une application sans avoir à installer entièrement l’application en local. Exemples d’implémentations incluent Citrix XenApp et Microsoft Application Virtualization (App-V). La diffusion d’application, l’accès à distance aux applications et les modes de virtualisation mixte (par exemple, application Remoting dans l’accès à distance complet au bureau) ne sont pas pris en charge.

Pour permettre l’extensibilité, le plug-in Lync VDI a été conçu pour utiliser les API indépendantes des plateformes appelées canaux virtuels dynamiques (DVC). Pour les scénarios qui ne sont pas explicitement pris en charge par Lync, reportez-vous aux instructions de prise en charge du fournisseur de solution VDI.

</div>

<div>

## <a name="known-feature-limitations"></a>Limitations des fonctionnalités connues

Les limitations suivantes sont connues lorsque vous utilisez Lync 2013 dans un environnement VDI :

  - La prise en charge des fonctionnalités d’anonymisation de l’agent Response Group et de délégation d’appel est limitée.

  - Il n’existe pas de prise en charge pour les fonctionnalités suivantes :
    
      - pages de réglage des périphériques audio et vidéo intégrés ;
    
      - Vidéo en plusieurs vues.
    
      - enregistrement des conversations ;
    
      - Services Bureau à distance (RDS).
    
      - Participation anonyme à des réunions (c’est-à-dire, rejoindre des réunions Lync hébergées par une organisation qui ne se fédérer pas avec votre organisation).
    
      - Utilisation du plug-in Lync VDI avec un appareil Lync Phone Edition.
    
      - continuité des appels en cas de panne du réseau ;
    
      - Sonneries personnalisées et fonctionnalités d’attente musicale.

  - Le plug-in Lync VDI n’est pas pris en charge dans un environnement Microsoft 365 ou Office 365.

</div>

</div>

<span> </span>

</div>

</div>

</div>

