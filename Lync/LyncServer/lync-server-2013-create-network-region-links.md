---
title: 'Lync Server 2013 : création de liens de région réseau'
description: 'Lync Server 2013 : créer des liens de région réseau.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6510d252ac1534a3a8e9f14d56acc8d0d8b60a6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553933"
---
# <a name="create-network-region-links-in-lync-server-2013"></a>Créer des liens de région réseau dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Au sein d’un réseau, les régions sont liées par une connectivité au réseau étendu physique. Un *lien de région réseau* crée un lien entre deux régions configurées pour le contrôle d’admission des appels et définit les restrictions de bande passante sur le trafic audio et vidéo entre ces régions.

Pour plus d’informations sur l’utilisation des liaisons de région réseau, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

L’exemple de topologie possède un lien entre les régions Amérique du Nord et APAC et un lien entre les régions EMEA et APAC. Chacun de ces liens de région est limité par la bande passante de la connexion WAN, comme décrit dans la rubrique Region Link Bandwidth information table dans la section exemple : Regrouping [Your Requirements for Call Admission Control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) de la documentation de planification.

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a>Pour créer des liens de région de réseau à l’aide de Lync Server Management Shell

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez la cmdlet New-CsNetworkRegionLink pour créer des liens de région et appliquer des profils de stratégie de bande passante appropriés. Par exemple, exécutez :
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a>Pour créer des liens de région de réseau à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur le bouton de navigation **Lien de région**.

4.  Cliquez sur **Nouveau**.

5.  Sur la page **Nouveau lien de région**, cliquez sur **Nom**, puis tapez le nom du lien de région réseau.

6.  Cliquez sur **région réseau \# 1**, puis sur la région réseau dans la liste que vous souhaitez lier à la région réseau \# 2.

7.  Cliquez sur **région réseau \# 2**, puis sur une région réseau dans la liste que vous souhaitez lier à la région réseau \# 1.

8.  Si vous le souhaitez, vous pouvez cliquer sur **Stratégie de bande passante**, puis sélectionner le profil de stratégie de bande passante que vous souhaitez appliquer au lien de région réseau.
    
    <div class=" ">
    

    > [!NOTE]  
    > Appliquez une stratégie de bande passante uniquement si le lien de région réseau est contraint par la bande passante et que vous souhaitez utiliser le contrôle d’admission des appels pour contrôler le trafic multimédia sur ce lien.

    
    </div>

9.  Cliquez sur **Valider**.

10. Pour finir de créer des liens région réseau pour votre topologie, répétez les étapes 4 à 9 avec les paramètres d’autres régions.

</div>

</div>

<span> </span>

</div>

</div>

</div>
