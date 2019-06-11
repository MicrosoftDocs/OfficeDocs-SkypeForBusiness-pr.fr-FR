---
title: 'Lync Server 2013 : Création ou modification d’un site réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1afb986f88af11ee2020b760e0a6d65aabed838c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a>Création ou modification d’un site réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-24_

Les déploiements de contrôle d’admission des appels (CAC), de E9-1-1 et de contournement de média multimédias dépendent de la configuration des *sites réseau* qui sont définis dans et qui sont toujours associés à une région réseau. Un site réseau représente une succursale, un ensemble de bâtiments ou un campus. Les sites réseau représentent des collections de sous-réseaux avec une bande passante similaire.

Pour créer ou modifier des sites réseau, utilisez les procédures suivantes. Par exemple, si vous avez déjà créé des sites réseau pour une seule fonctionnalité vocale, vous n’avez pas besoin de créer de nouveaux sites réseau. les autres fonctions vocales utilisent les mêmes sites. Cependant, il est possible que vous soyez obligé de modifier la définition d’un site réseau existant pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé un site réseau pour E9-1-1, vous devez modifier le site réseau au cours du déploiement du contrôle d’admission des appels pour appliquer un profil de stratégie de bande passante.

<div>


> [!NOTE]  
> Le cas échéant, vous trouverez des exemples et des exigences spécifiques pour les sites réseau en ce qui concerne une fonctionnalité vocale avancée dans la documentation de déploiement pour chaque fonctionnalité: 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">Configurer les sites réseau pour le CAC dans Lync Server 2013</A></P></LI></UL>



</div>

Pour plus d’informations sur l’utilisation des sites réseau, voir la documentation Lync Server Management Shell pour les applets de commande suivantes:

  - [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a>Créer un site réseau

Créez une région réseau qui peut être utilisée par le contrôle d’admission des appels, le E9-1-1 ou le contournement multimédia.

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a>Pour créer un site réseau à l’aide de Management Shell

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande New-CsNetworkSite pour créer des sites réseau :
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    Par exemple :
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    Dans cet exemple, vous avez créé un site réseau appelé « Chicago » qui se trouve dans la région « NorthAmerica » (Amérique du Nord).
    
    <div>
    

    > [!NOTE]  
    > La région NorthAmerica doit toujours exister pour que cette commande s’exécute correctement.

    
    </div>

3.  Pour finir de créer des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a>Pour créer un site réseau en utilisant le panneau de configuration de Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

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

11. Pour finir de créer des sites réseau pour votre topologie, répétez les étapes 4 à 10 avec les paramètres pour d’autres sites.

</div>

</div>

<div>

## <a name="modify-a-network-site"></a>Modifier un site réseau

Modification d’une région réseau qui peut être utilisée par le contrôle d’admission des appels, E9-1-1 ou contournement multimédia.

<div>

## <a name="to-modify-a-network-site"></a>Pour modifier un site réseau

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande Set-CsNetworkSite pour modifier des sites réseau :
    
        Set-CsNetworkSite -Identity <string>
    
    Exemple :
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    Dans cet exemple, le site appelé « Albuquerque » est déplacé dans la région « NorthAmerica ». Pour modifier la configuration du site réseau afin de déployer le contrôle d’admission des appels, le système E9-1-1 ou la déviation du trafic multimédia, modifiez les paramètres du site réseau en exécutant l’applet de commande Set-CsNetworkSite avec le paramètre BWPolicyProfileID ou LocationPolicy, respectivement.
    
    <div>
    

    > [!NOTE]  
    > Même si le paramètre BypassID existe pour la déviation du trafic multimédia, nous vous recommandons vivement de ne pas remplacer les ID de contournement générés automatiquement. Vous n’avez pas besoin de spécifier des paramètres supplémentaires pour configurer un site réseau pour la déviation du trafic multimédia.

    
    </div>

3.  Pour finir de modifier des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a>Pour modifier un site réseau en utilisant le panneau de configuration de Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur le bouton de navigation **Site**.

4.  Dans le tableau, cliquez sur le site réseau que vous souhaitez modifier.

5.  Cliquez sur **Modifier**, puis sur **Afficher les détails…**.

6.  Dans la page **Modifier le site**, changez les valeurs des paramètres de ce site réseau comme il convient.

7.  Cliquez sur **Valider**.

8.  Pour finir de modifier les sites réseau, répétez les étapes 4 à 7 avec les paramètres pour d’autres sites.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

