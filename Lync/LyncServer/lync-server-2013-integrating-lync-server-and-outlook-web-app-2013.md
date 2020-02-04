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
ms.openlocfilehash: faa75694ecaac662a643d331a4efdf91b41223e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>Intégration de Microsoft Lync Server 2013 et Microsoft Outlook Web App 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-03_

Outre l’intégration avec Microsoft Outlook 2013, Microsoft Lync Server 2013 peut être entièrement intégré à Microsoft Outlook Web App 2013 ; entre autres choses, la messagerie instantanée et la présence dans Outlook Web App sont ajoutées, et votre liste de contacts unifiée doit être partagée entre Outlook Web App et Microsoft Lync 2013. Pour intégrer Lync Server 2013 et Outlook Web App, vous devez commencer par vérifier que le Runtime API managée de l' 4,0 API Exchange a été installé sur votre serveur principal Microsoft Exchange Server 2013. Pour permettre l’intégration de skype16_server et d’Outlook Web App, vous devez d’abord vérifier que le runtime Unified Communications Managed API 4.0 a été installé sur votre serveur principal nm-exch-15-formal Pour ce faire, recherchez la valeur de registre suivante :

HKEY\_local\_machine\\système\\de\\CurrentControlSet\\services CurrentControlSet\\OWA\\instantmessaging ImplementationDLLPath

ImplementationDLLPath doit pointer vers l’emplacement du dossier correspondant au fichier Microsoft.Rtc.Internal.Ucweb.dll. Si ce n’est pas le cas, ou si la valeur de Registre n’existe pas, téléchargez et installez le programme d’installation d’UCMA Runtime à partir du <http://www.microsoft.com/en-us/download/details.aspx?id=34992>Centre de téléchargement Microsoft. Cette page comporte également des informations sur l’installation du runtime UCMA.

**Compatibilité descendante**

Lync Server 2013 peut être intégré aux versions de Microsoft Exchange Server 2010 de la messagerie unifiée et d’Outlook Web App. Pour plus d’informations, reportez-vous à l’article déploiement de la messagerie UNIFIÉe Exchange locale pour [http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)fournir la messagerie vocale de Lync Server 2010 à l’adresse. Si vous intégrationz à Exchange 2010, vous ne disposez pas de fonctionnalités spécifiques de Lync Server telles que le magasin de contacts unifié et l’archivage Lync-to-Exchange.

Microsoft Lync 2013 peut également être utilisé en association avec Exchange 2010 et Outlook 2010. De nouveau, il est possible que de nouvelles fonctionnalités telles que le magasin de contacts unifié et les photos haute résolution ne soient pas disponibles pour les utilisateurs de Lync 2013. Ces nouvelles fonctionnalités nécessitent Lync Server 2013 et Exchange 2013.

**Création d’un pool d’applications approuvées pour Outlook Web App**

Si vous avez installé le service routeur de messagerie unifiée Microsoft Exchange et le service de messagerie unifiée Microsoft Exchange sur le même ordinateur, vous n’avez pas besoin de créer un pool d’applications approuvé pour Outlook Web App. (Cela suppose que le serveur en question héberge un plan de numérotation de messagerie unifiée SipName.) Si vous utilisez un ordinateur unique pour héberger ces deux services, vous pouvez passer à la section de ce document intitulée **activation de la messagerie instantanée dans Outlook Web App**.

Lync Server 2013 peut détecter automatiquement les serveurs Exchange qui hébergent un plan de numérotation de messagerie unifiée SipName ; ils sont automatiquement ajoutés à la liste des serveurs connus de Lync Server. Il n’est pas nécessaire de créer un pool d’applications digne de confiance et de l’ajouter à la liste de serveurs connus. En fait, cela entraînera l’arrêt de l’intégration d’Outlook Web App.

<div>


> [!NOTE]  
> C’est la raison pour laquelle la topologie du serveur Lync possède désormais deux entrées pour le même ordinateur : l’entrée découverte automatique et l’entrée ajoutée manuellement. Pour résoudre ce problème et permettre à Outlook Web App de fonctionner de nouveau, utilisez Windows PowerShell pour supprimer les entrées du pool approuvé et les applications approuvées associées au serveur. Pour plus d’informations, reportez-vous aux rubriques d’aide des applets de commande <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> et <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A>.



</div>

Si ces deux services s’exécutent sur des ordinateurs distincts, une fois que vous avez vérifié que le runtime de l’API managée de communications unifiées 4,0 est installé, vous devez créer un pool d’applications approuvé Lync Server et une application de confiance associée Outlook Web App ; le serveur sera ajouté à la liste serveurs connus. Pour ce faire, commencez par exécuter une commande similaire à celle-ci à partir de Lync Server Management Shell :

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

Dans la commande précédente, atl-owa-001.litwareinc.com est le nom de domaine complet du pool Outlook Web App. il doit s’agir du nom qui apparaît dans le champ nom de l’objet et le nom de l’objet (SAN) du certificat qui permet d’accéder à Outlook Web App. De même, atl-cs-001.litwareinc.com est le nom de domaine complet du pool Lync Server 2013 qui héberge le nouveau pool d’applications approuvées. Notez également que le site spécifié, Redmond, représente le SiteID du site du serveur Lync. Le SiteID n’est pas nécessairement le même que le DisplayName du site ; vous pouvez récupérer des SiteIDs pour vos sites Lync Server en exécutant la commande suivante à partir de Lync Server Management Shell :

    Get-CsSite | Select-Object DisplayName, SiteID

Après avoir créé le pool d’applications approuvées, utilisez une commande semblable à ce qui suit pour configurer une identité d’application et un port pour Outlook Web App :

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

Dans la commande précédente, ApplicationID est simplement un identificateur convivial utilisé pour différencier les applications approuvées. ApplicationID peut être une chaîne de texte qui ne contient pas d’espaces vides ou autres caractères interdits (pour être assuré de créer un identificateur valide, nous vous recommandons d’utiliser uniquement des lettres et des nombres lorsque vous définissez la valeur ApplicationID). La valeur affectée au paramètre Port est également laissée à la discrétion de l’administrateur : il peut s’agir de n’importe quel port réseau disponible.

Après la création de l’application fiable, vous devez exécuter la commande suivante pour activer les modifications apportées à la topologie de votre serveur Lync :

    Enable-CsTopology

Notez que vous devez également ajouter votre serveur de boîte aux lettres et votre serveur de messagerie Exchange à l’ensemble de vos plans de numérotation URI SIP. Les serveurs seront alors configurés en tant qu’homologues SIP approuvés avec la topologie ExUmRouting pour Lync Server.

**Activation de la messagerie instantanée sur Outlook Web App**

Lorsque Lync Server est correctement configuré, vous pouvez alors commencer à configurer Outlook Web App. La première étape de ce processus consiste à activer la messagerie instantanée sur tous vos répertoires virtuels Outlook Web App sur votre serveur principal. (Il est inutile d’activer la messagerie instantanée pour les répertoires virtuels sur vos serveurs principaux. En fait, nous vous conseillons de ne pas activer la messagerie instantanée sur vos serveurs principaux.) L’activation de la messagerie instantanée sur les serveurs d’accès client peut être activée en exécutant la commande suivante à partir d’Exchange Management Shell :

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> Par défaut, la messagerie instantanée est activée quand vous installez Outlook Web App ; en d’autres termes, la propriété InstantMessagingEnabled est définie sur True. Toutefois, vous devez exécuter la commande précédente pour définir le type de messagerie instantanée sur OCS. Par défaut, la propriété InstantMessagingType est définie sur None.



</div>

Ensuite, vous devez ajouter les deux lignes suivantes dans le fichier Web. config Outlook Web App (le fichier se trouve généralement dans le dossier\\C :\\Program\\Files Microsoft\\Exchange\\Server\\v15 ClientAccess OWA). Ces deux lignes doivent être ajoutées sous le \<nœud\> AppSettings dans le fichier Web. config, et cette procédure doit être effectuée uniquement sur les serveurs principaux dans lesquels Outlook Web App est installé :

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

Dans l’exemple ci-dessus, la valeur de IMCertificateThumbprint doit être l’empreinte numérique du certificat Exchange 2013 installé sur les serveurs principaux. Vous pouvez récupérer ces informations en exécutant la commande suivante à partir d’Exchange Management Shell :

    Get-ExchangeCertificate

Notez également que la valeur affectée à inservername est le nom de domaine complet du pool de serveurs Lync dans lequel vous avez créé le pool d’applications approuvé pour Outlook Web App.

Le certificat que vous utilisez pour Outlook Web App doit être un certificat approuvé par Lync Server. Pour garantir que le certificat sera approuvé par Lync Server et Exchange, vous devez utiliser votre autorité de certification interne pour créer un certificat sur le serveur de boîte aux lettres, en vous assurant que le nom de domaine complet du serveur est utilisé pour le nom du sujet et que ce nom de domaine complet apparaît dans t. champ nom de la personne dont le certificat est différent. Une fois créé, le certificat peut être importé vers les serveurs principaux. Le résultat net est que le même certificat est utilisé pour deux raisons : 1) communication entre la messagerie unifiée Exchange et Lync Server. et 2) intégration d’Outlook Web App et de Lync Server.

Après avoir mis à jour le fichier Web. config, exécutez la commande suivante sur le serveur principal Exchange afin de recycler le pool Outlook Web App :

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

Le message suivant s’affiche dans Exchange Management Shell lorsque le recyclage réussit :

    "MSExchangeOWAAppPool" successfully recycled

**Configuration des stratégies de boîte aux lettres Outlook Web App**

À ce stade, vous pouvez utiliser la commande suivante afin de configurer la messagerie instantanée pour la ou les stratégies de boîte aux lettres Outlook Web App appropriées. Par exemple, cette commande, exécutée sur l’un de vos serveurs de boîtes aux lettres, active la messagerie instantanée pour la stratégie par défaut :

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Quant à cette commande, elle active la messagerie instantanée pour toutes vos stratégies de boîte aux lettres Outlook Web App :

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Après l’activation de la stratégie de boîte aux lettres, tous les utilisateurs gérés par cette stratégie disposeront d’une intégration complète entre Lync Server et Outlook Web App, à condition que :

  - L’utilisateur dispose d’une boîte aux lettres sur Exchange 2013.

  - L’utilisateur a été activé pour Lync Server 2013.

  - l’utilisateur possède une adresse proxy SIP valide.

**Désactivation de la messagerie instantanée dans Outlook Web App**

Comme indiqué précédemment, la messagerie instantanée est activée par défaut dans Outlook Web App. Cela signifie que si vous n’intégrez pas Outlook Web App à Lync Server, les utilisateurs verront les icônes de présence vides et un message d’erreur chaque fois qu’ils se connecteront à Outlook Web App. Pour éviter ce problème, utilisez la commande Exchange Management Shell suivante pour désactiver la messagerie instantanée dans Outlook Web App :

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Vérification de l’intégration à Outlook Web App**

Pour vérifier si les fonctionnalités de messagerie instantanée et de présence ont été intégrées dans Outlook Web App, authentifiez-vous dans Outlook Web App 2013. Dans le coin supérieur droit de l’écran, vous voyez votre nom d’affichage Exchange. S’il existe une icône de présence en regard de votre nom (par exemple, une icône verte indiquant que votre statut actuel est disponible) indiquant que vous avez correctement intégré Lync Server et Outlook Web App.

Après vous être authentifié dans Outlook Web App, vérifiez si un événement portant l’ID d’événement 112 (et la source MSExchange OWA) a été écrit dans le journal des événements sur le serveur de boîtes aux lettres. Cet événement indique que le gestionnaire de points de terminaison de la messagerie instantanée a été correctement initialisé. Si la messagerie instantanée ne semble pas fonctionner, sur le serveur de boîte aux lettres, recherchez les fichiers journaux dans le dossier C\\: Program\\Files\\Microsoft Exchange\\Server\\v15\\journalisation d’OWA\\instantmessaging. Si le dossier Logging ou InstantMessaging n’existe pas, cela indique que l’intégration a échoué. Dans ce cas, vous pouvez utiliser le suivi SIPStack sur Lync Server (tous les niveaux et tous les indicateurs) pour essayer de déterminer l’échec de l’intégration.

</div>

<span> </span>

</div>

</div>

</div>

