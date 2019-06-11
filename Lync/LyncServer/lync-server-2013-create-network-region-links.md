---
title: 'Lync Server 2013: création de liens de région réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7715aa258c56e98789f12d3c057047d947fd3c51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a>Créer des liens de région réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-19_

Au sein d’un réseau, les régions sont liées par une connectivité au réseau étendu physique. Un *lien de région réseau* crée un lien entre deux régions configurées pour le contrôle d’admission des appels (CAC) et définit les limites de bande passante pour le trafic audio et vidéo entre ces régions.

Pour plus d’informations sur l’utilisation des liaisons de région réseau, voir la documentation Lync Server Management Shell pour les applets de commande suivantes:

  - [New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

L’exemple de topologie possède un lien entre les régions Amérique du Nord et APAC, ainsi qu’un lien entre les régions EMEA et APAC. Chacun de ces liens de région est limité par la bande passante WAN, comme décrit dans la table informations sur la bande passante liée à la région dans l' [exemple: rassemblement de vos exigences de contrôle d’admission des appels dans la section Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) de la documentation de planification.

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a>Pour créer des liaisons de région réseau à l’aide de Lync Server Management Shell

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande New-CsNetworkRegionLink pour créer des liens de région et appliquer des profils de stratégie de bande passante appropriés. Par exemple, exécutez :
    
      ```
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a>Pour créer des liens de région réseau à l’aide du panneau de configuration de Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur le bouton de navigation **Lien de région**.

4.  Cliquez sur **Nouveau**.

5.  Dans la page **Nouveau lien de région**, cliquez sur **Nom**, puis tapez le nom du lien de région réseau.

6.  Cliquez sur la ** \#région réseau 1**, puis cliquez sur la région réseau dans la liste que vous voulez lier à la \#région 2 du réseau.

7.  Cliquez sur la ** \#zone réseau 2**, puis cliquez sur une région réseau dans la liste que vous voulez lier à la \#région 1 du réseau.

8.  Si vous le souhaitez, vous pouvez cliquer sur **Stratégie de bande passante**, puis sélectionner le profil de stratégie de bande passante à appliquer au lien de région réseau.
    
    <div class=" ">
    

    > [!NOTE]  
    > N’appliquez une stratégie de bande passante que si le lien de région réseau est contraint par la bande passante et que vous souhaitez utiliser le contrôle d’admission des appels pour contrôler le trafic multimédia sur ce lien.

    
    </div>

9.  Cliquez sur **Valider**.

10. Pour finir de créer des liens région réseau pour votre topologie, répétez les étapes 4 à 9 avec les paramètres d’autres régions.

</div>

</div>

<span> </span>

</div>

</div>

</div>
