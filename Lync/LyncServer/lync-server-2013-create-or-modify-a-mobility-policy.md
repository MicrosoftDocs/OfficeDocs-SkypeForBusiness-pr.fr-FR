---
title: 'Lync Server 2013: création ou modification d’une stratégie de mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91d3f03735048ab4354db9653554b6227bb7399e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Création ou modification d’une stratégie de mobilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Vous pouvez créer ou modifier une stratégie de mobilité pour autoriser les utilisateurs mobiles à utiliser les appareils mobiles pris en charge pour les fonctionnalités Lync telles que la messagerie instantanée, la présence et les contacts. Vous pouvez créer ou modifier des stratégies de mobilité depuis le panneau de configuration de Lync Server 2013 ou Lync Server 2013 Management Shell

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>Pour créer une stratégie de mobilité avec le panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton navigation de la **stratégie de mobilité** .

4.  Dans la page **stratégie de mobilité** , cliquez sur **nouveau**, puis effectuez l’une des opérations suivantes:
    
    1.  Pour créer une stratégie de mobilité de site, cliquez sur **stratégie de site**, cliquez sur un site, cliquez sur **OK**, passez en revue les paramètres par défaut et, si vous le souhaitez, apportez les modifications souhaitées.
    
    2.  Pour créer une stratégie de mobilité des utilisateurs, cliquez sur stratégie de l' **utilisateur**, tapez un nom, passez en revue les paramètres par défaut et, si vous le souhaitez, apportez les modifications souhaitées.

5.  Cliquez sur **Valider**.

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>Pour modifier une stratégie de mobilité avec le panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton navigation de la **stratégie de mobilité** .

4.  Dans la page **stratégie de mobilité** , cliquez sur l’une des stratégies de mobilité existantes.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Modifiez les paramètres.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Création de stratégies d’accès externe à l’aide d’applets de cmdlet Windows PowerShell

Vous pouvez créer des stratégies de mobilité (à l’étendue du site ou l’étendue par utilisateur) à l’aide de Windows PowerShell et de l’applet **de nouvelle cmdlet New-CsMobilityPolicy** . De plus, vous pouvez utiliser l’applet de passe **Set-CsMobilityPolicy** pour modifier l’une de vos stratégies existantes, y compris la stratégie globale. Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>Pour créer une stratégie de mobilité sur l’étendue du site

  - Cette commande crée une nouvelle stratégie de mobilité pour le site de Redmond:
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Dans la mesure où aucun paramètre (autre que le paramètre d’identité obligatoire) n’a été spécifié dans la commande précédente, les stratégies utilisent les valeurs par défaut de toutes les propriétés.

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>Pour créer une stratégie de mobilité pour l’étendue par utilisateur

  - Pour créer une stratégie de mobilité pour l’étendue par utilisateur, spécifiez une identité unique pour la stratégie:
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>Pour modifier une valeur de propriété unique lors de la création d’une stratégie de mobilité

  - Pour créer des stratégies qui utilisent des valeurs de propriété différentes, incluez le paramètre et la valeur de paramètre appropriés. Par exemple, cette commande crée une stratégie de mobilité qui désactive l’appel via le Bureau:
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>Pour modifier plusieurs valeurs de propriétés lors de la création d’une stratégie de mobilité

  - Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande crée une stratégie qui désactive la mobilité et l’appel via le Bureau:
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

Pour plus d’informations, consultez la rubrique d’aide pour les applets de [nouvelle-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) et [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration de la stratégie de mobilité dans Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

