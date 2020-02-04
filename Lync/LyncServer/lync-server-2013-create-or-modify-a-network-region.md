---
title: 'Lync Server 2013 : création ou modification d’une région réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75011a28567da8a6e386c42f272ee1510b8ceddc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>Créer ou modifier une région réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Les *régions réseau* sont les concentrateurs réseau ou les dorsales utilisés dans la configuration de contrôle d’admission des appels, de E9-1-1 et de contournement de média. Utilisez les procédures suivantes pour créer ou modifier des régions réseau. Par exemple, si vous avez déjà créé des régions réseau pour une seule fonctionnalité vocale, vous n’avez pas besoin de créer de nouvelles régions réseau. d’autres fonctionnalités avancées de voix entreprise utiliseront les mêmes régions réseau. Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé des régions réseau pour le service E9-1-1 (régions n’exigeant aucun site central associé), puis que vous déployez le contrôle d’admission des appels, vous devez modifier les définitions des régions réseau afin de spécifier un site central. Pour plus d’informations, voir [configurer des régions réseau pour CAC dans Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).

<div>


> [!NOTE]  
> Les exigences spécifiques aux fonctionnalités relatives aux définitions de zones réseau sont décrites dans les rubriques de déploiement de la fonctionnalité.



</div>

Pour plus d’informations sur l’utilisation des régions réseau, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>Créer une zone réseau

Créez une région réseau qui peut être utilisée par le contrôle d’admission des appels, le E9-1-1 ou le contournement multimédia.

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>Pour créer une région réseau à l’aide de Lync Server Management Shell

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande New-CsNetworkRegion pour créer des régions réseau :
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Par exemple :
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    Dans cet exemple, vous avez créé une région réseau appelée « NorthAmerica » (Amérique du Nord) associée à un site central avec l’ID de site CHICAGO.

3.  Pour finir de créer des régions réseau pour votre topologie, répétez l’étape 2 avec des paramètres pour chaque région réseau.

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>Pour créer une région réseau à l’aide du panneau de configuration de Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur **Région**.

4.  Cliquez sur **Nouveau**.

5.  Dans la page **Nouvelle région**, cliquez sur **Nom**, puis tapez le nom de la région réseau.

6.  Cliquez sur **Site central**, puis cliquez sur un site central dans la liste.

7.  Éventuellement, cliquez sur **Description**, puis tapez des informations supplémentaires pour décrire ce site réseau.

8.  Cliquez sur **Valider**.

9.  Pour finir de créer des régions réseau pour votre topologie, répétez les étapes 4 à 8 avec des paramètres pour d’autres régions.

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>Modifier une région de réseau

Modifiez les paramètres d’une région réseau existante afin de prendre en compte les modifications apportées aux informations de la région de base ou aux modifications requises par une nouvelle fonctionnalité.

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>Pour modifier une région réseau à l’aide de Lync Server Management Shell

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande Set-CsNetworkRegion pour modifier une région réseau existante :
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Exemple :
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    Dans cet exemple, vous avez modifié une région réseau existante appelée « NorthAmerica » (créée en suivant les procédures décrites plus haut dans cette rubrique) en changeant sa description. Si une description existait dans la région « NorthAmerica », cette commande la remplace par cette valeur. Si aucune description n’a été définie, cette commande s’en charge.

3.  Pour modifier d’autres régions réseau, répétez l’étape 2 avec les paramètres d’autres régions.

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>Pour modifier une région réseau à l’aide du panneau de configuration de Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur le bouton de navigation **Région**.

4.  Dans le tableau, cliquez sur la région réseau que vous souhaitez modifier.

5.  Cliquez sur **Modifier**, puis sur **Afficher les détails…**.

6.  Dans la page **Modifier la région**, changez les valeurs des paramètres de cette région réseau comme il convient.

7.  Cliquez sur **Valider**.

8.  Pour finir de modifier les régions réseau, répétez les étapes 4 à 7 avec des paramètres pour d’autres régions.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

