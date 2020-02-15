---
title: Lync Server 2013 ; Créer des itinéraires inter-région réseau
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
ms.openlocfilehash: 2259f47608b09ad7cff54ee0dc9b6be57502ee10
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>Créer des itinéraires inter-région réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Un *itinéraire inter-région réseau* définit l’itinéraire entre deux régions réseau. Chaque paire de régions réseau dans votre déploiement de contrôle d’admission des appels requiert un itinéraire inter-région réseau. Cela permet à chaque région réseau incluse dans le déploiement d’accéder à toute autre région.

Alors que les liens de région définissent les limitations de bande passante sur les connexions entre les régions, un itinéraire inter-région détermine le chemin lié qu’empruntera la connexion pour aller d’une région à l’autre.

Pour plus d’informations sur l’utilisation des itinéraires inter-région réseau, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

Dans l’exemple de topologie, les itinéraires inter-région réseau doivent être définis pour chacune des trois paires de régions : Amérique du Nord/EMEA, EMEA/APAC et Amérique du Nord/APAC.

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>Pour créer des itinéraires inter-région réseau à l’aide de Lync Server Management Shell

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

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
    > L’itinéraire inter-région réseau Amérique du Nord/APAC requiert deux liens de région réseau, car il n’existe aucun lien de région réseau direct entre elles.

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>Pour créer des itinéraires inter-région réseau à l’aide du panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur le bouton de navigation **Itinéraire de région**.

4.  Cliquez sur **Nouveau**.

5.  Dans la page **Nouvel itinéraire de région**, cliquez sur **Nom**, puis tapez un nom pour l’itinéraire inter-région réseau.

6.  Cliquez sur **région \#réseau 1**, puis sur une région réseau dans la liste que vous souhaitez acheminer vers la région \#réseau 2.

7.  Cliquez sur **région \#réseau 2**, puis sur une région réseau dans la liste que vous souhaitez acheminer vers la région \#réseau 1.

8.  Cliquez sur **Ajouter** en regard du champ **Liens de région réseau**, puis ajoutez un lien de région réseau qui sera utilisé dans l’itinéraire inter-région réseau.
    
    <div class=" ">
    

    > [!NOTE]  
    > Si vous créez un itinéraire pour deux régions réseau qui n’ont pas de lien de région réseau direct entre elles, vous devez ajouter tous les liens nécessaires pour terminer l’itinéraire. Par exemple, l’itinéraire inter-région réseau Amérique du Nord/APAC requiert deux liens de région réseau, car il n’existe aucun lien de région réseau direct entre elles.

    
    </div>

9.  Cliquez sur **Valider**.

10. Pour terminer la création des itinéraires inter-région réseau pour votre topologie, répétez les étapes 4 à 9 en spécifiant les paramètres correspondant à d’autres itinéraires inter-région réseau.

</div>

</div>

<span> </span>

</div>

</div>

</div>

