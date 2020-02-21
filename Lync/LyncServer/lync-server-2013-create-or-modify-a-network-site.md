---
title: 'Lync Server 2013 : création ou modification d’un site réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb449bcd0519338408eb596784707069d9a07415
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a>Création ou modification d’un site réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

Les déploiements du contrôle d’admission des appels, du système E9-1-1 et du contournement de média s’appuient sur la configuration des *sites réseau* qui sont définis dans une région du réseau et toujours associés à celle-ci. Un site réseau représente une succursale, un ensemble de bâtiments ou un campus. Les sites réseau représentent des ensembles de sous-réseaux avec une bande passante similaire.

Les procédures suivantes vous permettent de créer ou de modifier des sites réseau. Par exemple, si vous avez créé des sites réseau pour une fonctionnalité vocale, vous n’avez pas besoin de créer d’autres sites réseau ; les autres fonctionnalités vocales utiliseront ces mêmes sites. Toutefois, il est possible que vous soyez obligé de modifier la définition d’un site réseau existant pour appliquer des paramètres spécifiques à une fonctionnalité.  Par exemple, si vous avez créé un site réseau pour E9-1-1, vous devez modifier le site réseau au cours du déploiement du contrôle d’admission des appels pour appliquer un profil de stratégie de bande passante.

<div>


> [!NOTE]  
> Vous pouvez trouver des exemples et des conditions spécifiques pour les sites réseau concernant chaque fonctionnalité vocale avancée dans la documentation de déploiement : 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">Configuration des sites réseau pour le contrôle d’admission des adresses dans Lync Server 2013</A></P></LI></UL>



</div>

Pour plus d’informations sur l’utilisation des sites réseau, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - [New-applet csnetworksite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [Get-applet csnetworksite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [Set-applet csnetworksite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [Remove-applet csnetworksite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a>Créer un site réseau

Créez une région réseau pouvant être utilisée par le contrôle d’admission des appels, le système E9-1-1 ou le contournement de média.

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a>Pour créer un site réseau à l’aide de Lync Server Management Shell

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande New-CsNetworkSite pour créer des sites réseau :
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    Par exemple :
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    Dans cet exemple, vous avez créé un site réseau appelé « Chicago » qui se trouve dans la région « NorthAmerica » (Amérique du Nord).
    
    <div>
    

    > [!NOTE]  
    > La région NorthAmerica doit toujours exister pour que cette commande s’exécute correctement.

    
    </div>

3.  Pour finir de créer des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a>Pour créer un site réseau à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur le bouton de navigation **Site**.

4.  Cliquez sur **Nouveau**.

5.  Dans la page **Nouveau site**, cliquez sur **Nom**, puis tapez le nom du site réseau.

6.  Cliquez sur **Région**, puis cliquez sur une région dans la liste.

7.  Éventuellement, cliquez sur **Stratégie de bande passante**, puis sur une stratégie de bande passante dans la liste.
    
    <div>
    

    > [!NOTE]  
    > La stratégie de bande passante est uniquement requise si vous déployez le contrôle d’admission des appels sur le site.

    
    </div>

8.  Éventuellement, cliquez sur **Stratégie d’emplacement**, puis sur une stratégie d’emplacement dans la liste.
    
    <div>
    

    > [!NOTE]  
    > La stratégie d’emplacement est uniquement requise si vous déployez le système E9-1-1 sur le site.

    
    </div>

9.  Éventuellement, cliquez sur **Description**, puis tapez des informations supplémentaires pour décrire ce site réseau.

10. Cliquez sur **Valider**.

11. Pour finir de créer des sites réseau pour votre topologie, répétez les étapes 4 à 10 avec les paramètres pour d’autres sites.

</div>

</div>

<div>

## <a name="modify-a-network-site"></a>Modifier un site réseau

Modifiez une région réseau pouvant être utilisée par le contrôle d’admission des appels, le système E9-1-1 ou le contournement de média.

<div>

## <a name="to-modify-a-network-site"></a>Pour modifier un site réseau

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande Set-CsNetworkSite pour modifier des sites réseau :
    
        Set-CsNetworkSite -Identity <string>
    
    Par exemple :
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    Dans cet exemple, le site appelé « Albuquerque » est déplacé dans la région « NorthAmerica ». Pour modifier la configuration du site réseau afin de déployer le contrôle d’admission des appels, le système E9-1-1 ou le contournement de média, modifiez les paramètres du site réseau en exécutant l’applet de commande Set-CsNetworkSite avec le paramètre BWPolicyProfileID ou LocationPolicy, respectivement.
    
    <div>
    

    > [!NOTE]  
    > Bien que le paramètre BypassID existe pour le contournement de média, nous vous recommandons vivement de ne pas remplacer les ID de contournement générés automatiquement. Vous n’avez pas besoin de spécifier des paramètres supplémentaires pour configurer un site réseau pour le contournement de média.

    
    </div>

3.  Pour finir de modifier des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a>Pour modifier un site réseau à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur le bouton de navigation **Site**.

4.  Dans le tableau, cliquez sur le site réseau que vous souhaitez modifier.

5.  Cliquez sur **Modifier**, puis sur **Afficher les détails…**.

6.  Dans la page **Modifier le site**, changez les valeurs des paramètres de ce site réseau comme il convient.

7.  Cliquez sur **Valider**.

8.  Pour finir de modifier les sites réseau, répétez les étapes 4 à 7 avec les paramètres pour d’autres sites.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

