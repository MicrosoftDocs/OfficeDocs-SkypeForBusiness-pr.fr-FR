---
title: 'Lync Server 2013 : afficher les règles de stratégie de version du client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b43075fbd730134a9076273009714b682692994
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-client-version-policy-rules-in-lync-server-2013"></a>Afficher les règles de stratégie de version des clients dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Une stratégie de version de client est composée d’un ensemble de règles de stratégie de version de client. Ces règles définissent les actions à effectuer lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques. Vous pouvez afficher les règles de stratégie de version des clients à partir du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a>Pour afficher les règles de stratégie de version des clients à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **stratégie de version du client** .

4.  Sur la page **stratégie de version du client** , double-cliquez sur une stratégie de version de client que vous souhaitez afficher.

5.  Les règles s’affichent dans la page **modifier la stratégie de version du client** . Pour afficher les détails d’une règle, sélectionnez-la, puis cliquez sur **afficher les détails**.

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a>Affichage des règles de stratégie de version des clients à l’aide des applets de commande Windows PowerShell

Vous pouvez afficher les règles de stratégie de version des clients à l’aide de Lync Server Management Shell et de la cmdlet **Get-CsClientVersionPolicyRule** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-view-client-version-policy-rules"></a>Pour afficher les règles de stratégie de version des clients

  - Pour afficher les règles de stratégie de version des clients, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsClientVersionPolicyRule
    
    Cela renverra des informations similaires à celles-ci pour chaque règle configurée :
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

