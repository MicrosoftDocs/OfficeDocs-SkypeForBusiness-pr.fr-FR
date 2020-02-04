---
title: Lync Server 2013 ; Créer des itinéraires de réseau interrégion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 3909c41328e18302ef1104ac05d9a7c7987f57d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>Créer des itinéraires réseau interrégion dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Un *itinéraire réseau interrégional* définit l’itinéraire entre deux régions du réseau. Chaque paire de zones réseau dans le déploiement de votre contrôle d’admission des appels nécessite un itinéraire réseau interrégional. Cela permet à chaque région réseau incluse dans le déploiement d’accéder à toute autre région.

Lorsque les liaisons de zone définissent des limitations de bande passante pour les connexions entre les régions, un itinéraire interrégional détermine le chemin d’accès lié que la connexion traverse d’une région à l’autre.

Pour plus d’informations sur l’utilisation des itinéraires réseau interrégional, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

Dans l’exemple de topologie, des itinéraires réseau interrégion doivent être définis pour chacune des paires de trois régions : Amérique du Nord/EMEA, EMEA/APAC et Amérique du Nord/APAC.

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>Pour créer des itinéraires réseau interrégion à l’aide de Lync Server Management Shell

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande **New-CsNetworkInterRegionRoute** pour définir les itinéraires nécessaires. Par exemple, exécutez :
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > L’itinéraire interrégional du réseau Amérique du Nord et l’Asie du Nord nécessite deux liaisons de région réseau dans la mesure où il n’existe aucun lien de région réseau directe entre eux.

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>Pour créer des itinéraires réseau en utilisant le panneau de configuration de Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur le bouton de navigation **Itinéraire de région**.

4.  Cliquez sur **Nouveau**.

5.  Sur la page **nouveau routage de zone** , cliquez sur **nom** , puis tapez un nom pour l’itinéraire réseau interrégion.

6.  Cliquez sur **région \#réseau 1**, puis cliquez sur une région réseau dans la liste que vous voulez diriger vers la région \#2 du réseau.

7.  Cliquez sur **région \#2**du réseau, puis cliquez sur une région réseau dans la liste que vous voulez diriger vers la \#région 1 du réseau.

8.  Cliquez sur **Ajouter** à côté du champ liens entre les **zones du réseau** , puis ajoutez un lien de région réseau qui sera utilisé dans l’itinéraire réseau interrégion.
    
    <div class=" ">
    

    > [!NOTE]  
    > Si vous créez un itinéraire pour deux régions réseau qui n’ont pas de lien de région réseau direct entre elles, vous devez ajouter tous les liens nécessaires pour terminer l’itinéraire. Par exemple, l’itinéraire d’interrégion du réseau Amérique du Nord ou Pacifique nécessite deux liaisons de région réseau, car il n’y a pas de lien de région réseau directe entre eux.

    
    </div>

9.  Cliquez sur **Valider**.

10. Pour finaliser la création de itinéraires d’interrégion pour votre topologie, répétez les étapes 4 à 9 avec les paramètres des autres itinéraires réseau interrégion.

</div>

</div>

<span> </span>

</div>

</div>

</div>

