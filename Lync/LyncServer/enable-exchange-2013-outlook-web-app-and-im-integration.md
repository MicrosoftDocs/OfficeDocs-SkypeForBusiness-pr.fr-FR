---
title: Activation d’Outlook Web App et de l’intégration de la messagerie instantanée dans Exchange 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bd9fb94dd0f068547819aa884b608ac6ddf7e39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Activation d’Outlook Web App et de l’intégration de la messagerie instantanée dans Exchange 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Pour activer l’intégration de la messagerie instantanée et de l’intégration de la messagerie instantanée Exchange 2013 à Lync Server 2013, vous devez ajouter le serveur de serveur d’accès au client Exchange 2013 à la topologie Lync Server 2013 comme serveur d’applications de confiance.

<div>

## <a name="to-create-a-trusted-application-pool"></a>Pour créer un pool d’applications approuvé

1.  Démarrez Lync Server 2013 Management Shell.

2.  Exécutez l’applet de commande suivante :
    
        Get-CsSite
    
    Le siteID est alors renvoyé pour le siteName dans lequel vous créez le pool. Pour plus d’informations, reportez-vous à la rubrique [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) dans la documentation Lync Server 2013 Management Shell.

3.  Exécutez l’applet de commande suivante :
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Pour plus d’informations, reportez-vous à [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) dans la documentation de Lync Server 2013 Management Shell.
    
    Le nom de domaine complet du serveur Exchange doit être configuré en tant que nom du sujet du certificat OWA Exchange (SN) ou le nom de l’autre nom de l’objet.
    
    Dans Exchange OWA, vérifiez que le nom de domaine complet (FQDN) du pool est également approuvé.
    
    <div>
    

    > [!IMPORTANT]  
    > Si votre serveur CAS n’est <EM>pas</EM> localisé sur le même serveur qui exécute Exchange 2013 Unified Messaging (um), ignorez les étapes restantes de cette procédure et effectuez la procédure « créer une application sécurisée pour le serveur CAS Exchange 2013 », plus loin dans cette rubrique. Si votre serveur CAS est colocalisé sur le même serveur qui exécute Exchange 2013 Unified Messaging (UM), suivez les étapes décrites dans cette procédure et n’exécutez pas la procédure « créer une application fiable pour le serveur CAS Exchange 2013 », plus loin dans cette rubrique.

    
    </div>

4.  Exécutez **Enable-CsTopology**.

5.  Ouvrez le générateur de topologie et téléchargez la topologie existante.

6.  Dans le volet gauche, développez l’arborescence jusqu’à ce que vous atteigniez **serveurs d’application approuvés**.

7.  Développez le nœud **serveurs d’applications de confiance** .

8.  Le serveur Exchange 2013 CAS est désormais répertorié comme serveur d’applications de confiance.

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>Pour créer une application fiable pour le serveur CAS Exchange 2013

1.  Démarrez Lync Server 2013 Management Shell.

2.  Si votre serveur CAS n’est *pas* localisé sur le même serveur qui exécute Exchange 2013 Unified Messaging (um), exécutez l’applet de commande suivante :
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Pour plus d’informations, reportez-vous à la rubrique [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) dans la documentation de Lync Server 2013 Management Shell.

3.  Exécutez **Enable-CsTopology**.

4.  Dans le concepteur de topologies, dans le volet gauche, développez l’arborescence jusqu’à ce que vous atteigniez des **serveurs d’application approuvés**.

5.  Développez le nœud **serveurs d’applications de confiance** .

6.  Le serveur Exchange 2013 CAS est désormais répertorié comme serveur d’applications de confiance.

</div>

</div>

<span> </span>

</div>

</div>

</div>

