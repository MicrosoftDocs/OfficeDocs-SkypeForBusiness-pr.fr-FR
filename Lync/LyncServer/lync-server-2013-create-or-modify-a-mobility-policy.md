---
title: 'Lync Server 2013 : création ou modification d’une stratégie de mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4246569ad7d66788cef507488b78567b6b892f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Création ou modification d’une stratégie de mobilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez créer ou modifier une stratégie de mobilité pour permettre aux utilisateurs mobiles d’utiliser les périphériques mobiles pris en charge pour les fonctionnalités Lync, comme la messagerie instantanée, la présence et les contacts. Vous pouvez créer ou modifier des stratégies de mobilité à partir du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>Pour créer une stratégie de mobilité avec le panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Stratégie de mobilité**.

4.  Sur la page **stratégie de mobilité** , cliquez sur **nouveau**, puis effectuez l’une des opérations suivantes :
    
    1.  Pour créer une stratégie de mobilité de site, cliquez sur **Stratégie de site**, cliquez sur un site, cliquez sur **OK**, vérifiez les paramètres par défaut, puis, le cas échéant, effectuez les modifications nécessaires.
    
    2.  Pour créer une stratégie de mobilité utilisateur, cliquez sur **Stratégie de l’utilisateur**, tapez un nom, vérifiez les paramètres par défaut, puis, le cas échéant, effectuez les modifications nécessaires.

5.  Cliquez sur **Valider**.

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>Pour modifier une stratégie de mobilité avec le panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Stratégie de mobilité**.

4.  Sur la page **stratégie de mobilité** , cliquez sur l’une des stratégies de mobilité existantes.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Modifiez les paramètres de votre choix.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Création de stratégies d’accès externe à l’aide d’applets de commande Windows PowerShell

Vous pouvez créer des stratégies de mobilité (au niveau de l’étendue site ou par utilisateur) à l’aide de Windows PowerShell et de la cmdlet **New-CsMobilityPolicy** . De plus, vous pouvez utiliser la cmdlet **Set-CsMobilityPolicy** pour modifier l’une de vos stratégies existantes, notamment la stratégie globale. Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>Pour créer une stratégie de mobilité au niveau de l’étendue site

  - Cette commande crée une stratégie de mobilité pour le site Redmond :
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Étant donné qu’aucun paramètre n’est spécifié dans la commande précédente (sauf le paramètre obligatoire Identity), les stratégies utiliseront les valeurs par défaut pour toutes ses propriétés.

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>Pour créer une stratégie de mobilité au niveau de l’étendue utilisateur

  - Pour créer une stratégie de mobilité sur l’étendue Utilisateur, spécifiez un paramètre Identity unique pour la stratégie :
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>Pour modifier une seule valeur de propriété lors de la création d’une stratégie de mobilité

  - Pour créer des stratégies utilisant différentes valeurs de propriétés, incluez le paramètre et la valeur de paramètre appropriés. Par exemple, cette commande crée une stratégie de mobilité désactivant la fonctionnalité Appel via le bureau :
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>Pour modifier plusieurs valeurs de propriété lors de la création d’une stratégie de mobilité

  - Plusieurs valeurs de propriété peuvent être modifiées en incluant plusieurs paramètres. Par exemple, cette commande crée une stratégie désactivant à la fois la mobilité et la fonctionnalité Appel via le bureau :
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

Pour plus d’informations, recherchez les cmdlets [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) et [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) dans la rubrique d’aide.

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

