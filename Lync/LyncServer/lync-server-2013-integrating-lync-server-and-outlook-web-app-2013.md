---
title: 'Lync Server 2013 : intégration de Lync Server et d’Outlook Web App 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44de5139d3ad8f38c5177a18260045fda7abdeea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>Intégration de Microsoft Lync Server 2013 et de Microsoft Outlook Web App 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-03_

En plus de l’intégration à Microsoft Outlook 2013, Microsoft Lync Server 2013 peut être entièrement intégré à Microsoft Outlook Web App 2013 ; entre autres, cela ajoute la messagerie instantanée et la présence à Outlook Web App, et permet de partager votre liste de contacts unifiée entre Outlook Web App et Microsoft Lync 2013. Pour intégrer Lync Server 2013 et Outlook Web App, vous devez d’abord vérifier que le runtime Unified Communications Managed API 4,0 est installé sur votre serveur principal Microsoft Exchange Server 2013. Pour ce faire, recherchez l’existence de la valeur de Registre suivante :

HKEY\_local\_machine\\System\\CurrentControlSet\\services\\MSExchange OWA\\instantmessaging\\ImplementationDLLPath

Le ImplementationDLLPath doit pointer vers l’emplacement du dossier correspondant au fichier Microsoft. RTC. Internal. UCWeb. dll. Si ce n’est pas le cas, ou si la valeur de Registre n’existe pas, vous devez télécharger et installer le programme d’installation d’UCMA Runtime à <http://www.microsoft.com/download/details.aspx?id=34992>partir du centre de téléchargement Microsoft à l’adresse. Vous trouverez des informations sur la façon d’installer le runtime UCMA sur la même page Web.

**Compatibilité descendante**

Lync Server 2013 peut être intégré aux versions Microsoft Exchange Server 2010 de la messagerie unifiée et d’Outlook Web App. Pour plus d’informations, reportez-vous à l’article Deploying on-premises Exchange UM [http://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)to propose Lync Server 2010 voice mail à l’adresse. Si vous intégrez à Exchange 2010, vous ne disposerez pas de fonctionnalités spécifiques de Lync Server, telles que le magasin de contacts unifié et l’archivage Lync-vers-Exchange.

Microsoft Lync 2013 peut également être utilisé conjointement avec Exchange 2010 et Outlook 2010. Cependant, une fois encore, les nouvelles fonctionnalités telles que le magasin de contacts unifié et les photos haute résolution ne seront pas disponibles pour les utilisateurs de Lync 2013. Ces nouvelles fonctionnalités nécessitent Lync Server 2013 et Exchange 2013.

**Création d’un pool d’applications approuvées pour Outlook Web App**

Si vous avez installé le service de routeur d’appels de messagerie unifiée Microsoft Exchange et le service de messagerie unifiée Microsoft Exchange sur le même ordinateur, il n’est pas nécessaire de créer un pool d’applications approuvées pour Outlook Web App. (Cela suppose que le serveur en question héberge un plan de numérotation de messagerie unifiée SipName.) Si vous utilisez un seul ordinateur pour héberger ces deux services, vous pouvez passer à la section de ce document intitulée activation de la **messagerie instantanée sur Outlook Web App**.

Lync Server 2013 permet de découvrir automatiquement tous les serveurs Exchange qui hébergent un plan de numérotation de messagerie unifiée SipName ; ces serveurs sont automatiquement ajoutés à la liste des serveurs connus Lync Server. Il n’est pas nécessaire de créer un pool d’applications approuvées et d’ajouter ces serveurs à la liste des serveurs connus. En fait, cette opération entraîne l’arrêt de l’intégration d’Outlook Web App.

<div>


> [!NOTE]  
> Cela est dû au fait que la topologie Lync Server dispose désormais de deux entrées pour le même ordinateur : l’entrée découverte automatique et l’entrée ajoutée manuellement. Pour résoudre le problème, et pour que Outlook Web App fonctionne à nouveau, utilisez Windows PowerShell pour supprimer le pool approuvé et les entrées d’applications approuvées pour le serveur. Pour plus d’informations, consultez les rubriques d’aide pour les applets de commande <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> et <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> .



</div>

Si ces deux services s’exécutent sur des ordinateurs distincts, une fois que vous avez vérifié que le runtime Unified Communications Managed API 4,0 est installé, vous devez créer un pool d’applications approuvées Lync Server et une application approuvée associée à Outlook Web App ; Cela permet d’ajouter le serveur à la liste des serveurs connus. Pour ce faire, exécutez d’abord une commande similaire à celle-ci dans Lync Server Management Shell :

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

Dans la commande précédente, atl-owa-001.litwareinc.com est le nom de domaine complet du pool Outlook Web App ; il doit s’agir du même nom qui s’affiche dans les champs nom de l’objet et autre nom de l’objet (SAN) du certificat qui fournit l’accès à Outlook Web App. De même, atl-cs-001.litwareinc.com est le nom de domaine complet du pool Lync Server 2013 qui hébergera le nouveau pool d’applications approuvées. Notez également que le site spécifié, Redmond, représente le SiteID du site Lync Server. Le SiteID n’est pas nécessairement identique au DisplayName du site ; vous pouvez récupérer SiteIDs pour vos sites Lync Server en exécutant la commande suivante à partir de Lync Server Management Shell :

    Get-CsSite | Select-Object DisplayName, SiteID

Après avoir créé le pool d’applications approuvées, utilisez une commande similaire à celle qui suit pour configurer une identité d’application et un port pour Outlook Web App :

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

Dans la commande précédente, ApplicationID est simplement un identificateur convivial utilisé pour différencier les applications approuvées. ApplicationID peut être une chaîne de texte qui ne contient pas d’espaces vides ou autres caractères interdits. (Pour être assuré de créer un identificateur valide, nous vous recommandons d’utiliser uniquement des lettres et des nombres quand vous spécifiez ApplicationID.) La valeur affectée au paramètre Port est également laissée à la discrétion de l’administrateur : il peut s’agir de n’importe quel port réseau disponible.

Après avoir créé l’application approuvée, vous devez exécuter la commande suivante pour activer les modifications apportées à votre topologie Lync Server :

    Enable-CsTopology

Notez que vous devez également ajouter votre serveur d’accès au client Exchange et votre serveur de boîtes aux lettres à tous vos plans de numérotation URI SIP. Ensuite, les serveurs sont configurés comme homologues SIP approuvés avec la topologie ExUmRouting pour Lync Server.

**Activation de la messagerie instantanée sur Outlook Web App**

Avec Lync Server correctement configuré, vous pouvez commencer à configurer Outlook Web App. La première étape de ce processus consiste à activer la messagerie instantanée sur tous vos répertoires virtuels Outlook Web App sur vos serveurs frontaux. (Il n’est pas nécessaire d’activer la messagerie instantanée pour les répertoires virtuels sur vos serveurs principaux. En fait, il est recommandé de ne pas activer la messagerie instantanée sur vos serveurs principaux.) La messagerie instantanée peut être activée sur les serveurs d’accès au client en exécutant la commande suivante à partir de l’environnement de commande Exchange Management Shell :

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> Par défaut, la messagerie instantanée est activée lors de l’installation d’Outlook Web App ; autrement dit, la propriété InstantMessagingEnabled est définie sur true. Toutefois, vous devez toujours exécuter la commande précédente pour définir le type de messagerie instantanée sur OCS. Par défaut, InstantMessagingType est défini sur None.



</div>

Ensuite, vous devez ajouter les deux lignes suivantes au fichier Web. config d’Outlook Web App (ce fichier se trouve généralement dans le dossier\\C :\\Program\\Files Microsoft\\Exchange\\Server\\v15 du client ClientAccess OWA). Ces deux lignes doivent être ajoutées sous le \<nœud\> AppSettings dans le fichier Web. config, et cette procédure doit être effectuée uniquement sur les serveurs principaux où Outlook Web App a été installé :

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

Dans l’exemple précédent, la valeur de IMCertificateThumbprint doit être l’empreinte du certificat Exchange 2013 installé sur vos serveurs principaux. Vous pouvez récupérer ces informations en exécutant la commande suivante à partir de l’environnement de commande Exchange Management Shell :

    Get-ExchangeCertificate

Notez également que la valeur affectée à imservername est le nom de domaine complet du pool Lync Server où vous avez créé le pool d’applications approuvées pour Outlook Web App.

Le certificat que vous utilisez pour Outlook Web App doit être un certificat approuvé par Lync Server. Pour vous assurer que le certificat sera approuvé par Lync Server et Exchange, utilisez votre autorité de certification interne pour créer un certificat sur le serveur de boîtes aux lettres, en vous assurant que le nom de domaine complet du serveur est utilisé pour le nom de sujet et que ce nom de domaine complet apparaît dans t champ autre nom du certificat. Une fois que le certificat a été créé, il peut être importé sur vos serveurs principaux. En effet, le même certificat est utilisé à deux fins : 1) communication entre la messagerie unifiée Exchange et Lync Server ; et, 2) l’intégration entre Outlook Web App et Lync Server.

Une fois que vous avez mis à jour le fichier Web. config, vous devez exécuter la commande suivante sur le serveur principal Exchange afin de recycler le pool Outlook Web App :

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

Si l’opération de recyclage réussit, vous verrez le message suivant s’afficher dans l’environnement de commande Exchange Management Shell :

    "MSExchangeOWAAppPool" successfully recycled

**Configuration des stratégies de boîte aux lettres Outlook Web App**

À ce stade, vous pouvez utiliser la commande suivante pour configurer la messagerie instantanée sur la ou les stratégies de boîte aux lettres Outlook Web App appropriées. Par exemple, cette commande, exécutée sur l’un de vos serveurs de boîtes aux lettres, active la messagerie instantanée sur la stratégie par défaut :

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Cette commande active la messagerie instantanée pour toutes vos stratégies de boîte aux lettres Outlook Web App :

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Une fois la stratégie de boîte aux lettres activée, tous les utilisateurs gérés par cette stratégie disposent d’une intégration complète entre Lync Server et Outlook Web App, à condition que :

  - L’utilisateur dispose d’une boîte aux lettres sur Exchange 2013.

  - L’utilisateur a été activé pour Lync Server 2013.

  - l’utilisateur possède une adresse proxy SIP valide.

**Désactivation de la messagerie instantanée dans Outlook Web App**

Comme indiqué précédemment, la messagerie instantanée est activée par défaut dans Outlook Web App. Cela signifie que, si vous n’intégrez pas Outlook Web App à Lync Server, les utilisateurs verront des icônes de présence vides et un message d’erreur chaque fois qu’ils se connectent à Outlook Web App. Pour éviter ce problème, utilisez la commande Exchange Management Shell suivante pour désactiver la messagerie instantanée dans Outlook Web App :

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Vérification de l’intégration à Outlook Web App**

Pour vérifier que la messagerie instantanée et la présence ont été intégrées à Outlook Web App, connectez-vous à Outlook Web App 2013. Dans le coin supérieur droit de l’écran, vous voyez votre nom d’affichage Exchange. S’il existe une icône de présence en regard de votre nom (par exemple, une icône verte indiquant que votre statut actuel est disponible), ce qui indique que vous avez correctement intégré Lync Server et Outlook Web App.

Après l’authentification initiale sur Outlook Web App, vérifiez si un événement avec l’ID d’événement 112 (et la source MSExchange OWA) a été écrit dans le journal des événements sur le serveur de boîtes aux lettres. Cet événement indique que le gestionnaire de points de terminaison de messagerie instantanée a été correctement initialisé. Si la messagerie instantanée ne semble pas fonctionner, sur le serveur de boîtes aux lettres, recherchez les fichiers journaux dans le dossier C\\: Program\\Files\\Microsoft Exchange\\Server\\v15 du client\\Logging\\OWA instantmessaging. Si les dossiers journalisation ou InstantMessaging n’existent pas, cela signifie que l’intégration a échoué. Dans ce cas, vous pouvez utiliser le suivi SIPStack sur Lync Server (tous les niveaux et tous les indicateurs) pour essayer et déterminer pourquoi l’intégration a échoué.

</div>

<span> </span>

</div>

</div>

</div>

