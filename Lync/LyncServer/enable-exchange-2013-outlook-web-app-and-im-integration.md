---
title: Activer Exchange 2013 Outlook Web App et l’intégration de la messagerie instantanée
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
ms.openlocfilehash: da4289f663d62d1638c0f669e17a5e318e0788d3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Activer Exchange 2013 Outlook Web App et l’intégration de la messagerie instantanée

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Pour activer l’intégration d’Exchange 2013 Outlook Web Access (OWA) et de la messagerie instantanée avec Lync Server 2013, vous devez ajouter le serveur de serveur d’accès au client (CAS) Exchange 2013 à la topologie Lync Server 2013 en tant que serveur d’applications approuvées.

<div>

## <a name="to-create-a-trusted-application-pool"></a>Pour créer un pool d’applications approuvées

1.  Démarrez Lync Server 2013 Management Shell.

2.  Exécutez la cmdlet suivante :
    
        Get-CsSite
    
    Celle-ci renvoie la valeur siteID correspondant à la valeur siteName dans laquelle vous créez le pool. Pour plus d’informations, reportez-vous à [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) dans la documentation de Lync Server 2013 Management Shell.

3.  Exécutez la cmdlet suivante :
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Pour plus d’informations, reportez-vous à la rubrique [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) dans la documentation de Lync Server 2013 Management Shell.
    
    Le nom de domaine complet du serveur Exchange Server doit être configuré en tant que nom d’objet du certificat Exchange OWA ou en tant qu’autre nom de l’objet.
    
    Dans Exchange OWA, assurez-vous que le nom de domaine complet du pool est également approuvé.
    
    <div>
    

    > [!IMPORTANT]  
    > Si votre serveur CAS n’est <EM>pas</EM> colocalisé sur le même serveur qui exécute la messagerie unifiée Exchange 2013, ignorez les étapes restantes de cette procédure et exécutez la procédure « créer une application approuvée pour le serveur CAS Exchange 2013 » plus loin dans cette rubrique. Si votre serveur CAS est colocalisé sur le même serveur qui exécute la messagerie unifiée Exchange 2013, effectuez les étapes de cette procédure et n’effectuez pas la procédure « créer une application approuvée pour le serveur CAS Exchange 2013 » plus loin dans cette rubrique.

    
    </div>

4.  Exécutez **Enable-CsTopology**.

5.  Ouvrez le Générateur de topologie et téléchargez la topologie existante.

6.  Dans le volet gauche, développez l’arborescence jusqu’à ce que vous atteigniez **Serveurs d’applications approuvées**.

7.  Développez le nœud **Serveurs d’applications approuvées**.

8.  Vous devez maintenant voir le serveur CAS Exchange 2013 mentionné en tant que serveur d’applications approuvées.

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>Pour créer une application approuvée pour le serveur CAS Exchange 2013

1.  Démarrez Lync Server 2013 Management Shell.

2.  Si votre serveur CAS n’est *pas* colocalisé sur le même serveur qui exécute la messagerie unifiée Exchange 2013, exécutez l’applet de commande suivante :
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Pour plus d’informations, reportez-vous à la rubrique [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) dans la documentation de Lync Server 2013 Management Shell.

3.  Exécutez **Enable-CsTopology**.

4.  Dans le Générateur de topologie, dans le volet gauche, développez l’arborescence jusqu’à ce que vous atteigniez **Serveurs d’applications approuvées**.

5.  Développez le nœud **Serveurs d’applications approuvées**.

6.  Vous devez maintenant voir le serveur CAS Exchange 2013 mentionné en tant que serveur d’applications approuvées.

</div>

</div>

<span> </span>

</div>

</div>

</div>

