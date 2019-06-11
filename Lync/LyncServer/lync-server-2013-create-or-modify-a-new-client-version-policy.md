---
title: 'Lync Server 2013: création ou modification d’une stratégie de nouvelle version du client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64e9d9d2879d4633b1775f8934186b8b01992d13
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>Créer ou modifier une nouvelle stratégie de version de client dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Vous pouvez utiliser des stratégies de version de client pour spécifier les versions des clients qui sont prises en charge dans votre environnement. L’utilisation du contrôle de version du client peut vous aider à réduire les coûts associés à la prise en charge de plusieurs versions de client. Cela permet également d’améliorer l’utilisation globale de l’utilisateur, car lorsque les versions précédentes et ultérieures de clients interagissent, les fonctionnalités disponibles peuvent être limitées par la version antérieure du client. Vous pouvez créer ou modifier des stratégies de version de client à partir du panneau de configuration de Lync Server 2013 ou de Lync Server 2013 Management Shell.

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>Pour créer ou modifier des stratégies de version du client à l’aide du panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**.
    
    <div>
    

    > [!NOTE]  
    > L’onglet <STRONG>stratégie de version du client</STRONG> est sélectionné par défaut.

    
    </div>

4.  Dans la page **stratégie de version du client** , effectuez l’une des opérations suivantes:
    
      - Pour créer une stratégie de version de client, cliquez sur **nouveau**, sélectionnez **stratégie de site**, **stratégie de pool**ou stratégie de l' **utilisateur**, puis cliquez sur **OK**.
    
      - Pour modifier la stratégie globale ou une autre stratégie de version de client existante, sélectionnez la stratégie, cliquez sur **modifier**, puis sur **afficher les détails**.

5.  Dans la page **modifier la stratégie de version du client** , créez ou modifiez des règles comme décrit dans la rubrique [créer ou modifier une règle de stratégie de version de client dans Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>Création ou modification de stratégies de version de client à l’aide des cmdlets Windows PowerShell

Vous pouvez créer des stratégies de version du client à l’aide de l’applet **de nouvelle cmdlet New-CsClientVersionPolicy** , puis les modifier à l’aide de l’applet de contrôle **Set-CsClientVersionPolicy** . Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>Pour créer une stratégie de nouvelle version de client basée sur le site

  - La commande suivante crée une stratégie de nouvelle version du client appliquée au site de Redmond. Étant donné qu’aucun paramètre supplémentaire n’est spécifié, la nouvelle stratégie utilisera les paramètres de version de client par défaut.
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>Pour créer une nouvelle stratégie de version de client par utilisateur

  - Pour créer une stratégie par utilisateur, utilisez une commande similaire à celle-ci:
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

Pour plus d’informations, consultez les rubriques d’aide pour la cmdlet [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) et l’applet de connexion [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

