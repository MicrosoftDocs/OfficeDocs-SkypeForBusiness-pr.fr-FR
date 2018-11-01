---
title: Intégration de Microsoft Lync Server 2013 et Microsoft Outlook Web App 2013
TOCTitle: Intégration de Microsoft Lync Server 2013 et Microsoft Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49891350
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Intégration de Microsoft Lync Server 2013 et Microsoft Outlook Web App 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Outre l’intégration à Microsoft Outlook 2013, Microsoft Lync Server 2013 peut être entièrement intégré à Microsoft Outlook Web App 2013. Cela se traduit notamment par l’ajout des fonctionnalités de messagerie instantanée et de présence à Outlook Web App, ainsi que le partage de votre liste des contacts unifiée entre Outlook Web App et Microsoft Lync 2013. Pour permettre l’intégration de Lync Server 2013 et d’Outlook Web App, vous devez d’abord vérifier que le runtime Unified Communications Managed API 4.0 a été installé sur votre serveur principal Microsoft Exchange Server 2013. Pour ce faire, recherchez la valeur de Registre suivante :

HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

ImplementationDLLPath doit pointer vers l’emplacement du dossier correspondant au fichier Microsoft.Rtc.Internal.Ucweb.dll. Si ce n’est pas le cas ou si la valeur de Registre n’existe pas, vous devez télécharger et installer le programme d’installation du runtime UCMA à partir du Centre de téléchargement Microsoft à l’adresse suivante : <http://www.microsoft.com/fr-fr/download/details.aspx?id=34992>. Cette page comporte également des informations sur la façon d’installer le runtime UCMA.

**Compatibilité descendante**

Lync Server 2013 peut être intégré aux versions Microsoft Exchange Server 2010 de la messagerie unifiée et d’Outlook Web App. Pour plus d’informations, voir l’article Déploiement de la messagerie unifiée Exchange localement pour fournir la messagerie vocale Lync Server 2010, à l’adresse [http://technet.microsoft.com/fr-fr/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md). Si vous effectuez une intégration à Exchange 2010, vous ne disposerez pas de fonctionnalités propres à Lync Server telles que le magasin de contacts unifié et l’archivage de Lync vers Exchange.

Microsoft Lync 2013 peut également être utilisé conjointement avec Exchange 2010 et Outlook 2010. Cependant, dans ce cas également, de nouvelles fonctionnalités telles que le magasin de contact unifié et les photos haute résolution ne seront pas disponibles pour les utilisateurs Lync 2013. Ces nouvelles fonctionnalités nécessitent Lync Server 2013 et Exchange 2013.

**Création d’un pool d’applications approuvées pour Outlook Web App**

Si vous avez installé le service de routage d’appels vers la messagerie unifiée Microsoft Exchange et le service de messagerie unifiée Microsoft Exchange sur le même ordinateur, vous n’avez pas besoin de créer un pool d’applications approuvées pour Outlook Web App. (Le serveur en question est supposé héberger un plan de numérotation de messagerie unifiée SipName.) Si vous utilisez un même ordinateur pour héberger ces deux services, vous pouvez passer à la section de ce document intitulée **Activation de la messagerie instantanée sur Outlook Web App**.

Lync Server 2013 peut découvrir automatique tous les serveurs Exchange qui hébergent un plan de numérotation de messagerie unifiée SipName ; ces serveurs sont automatiquement ajoutés à la liste des serveurs connus Lync Server. Vous n’avez pas besoin de créer de pool d’applications approuvées et d’ajouter ces serveurs à la liste des serveurs connus. En fait, cela entraînerait l’arrêt de l’intégration d’Outlook Web App.

> [!NOTE]  
> En effet, la topologie Lync Server posséderait alors deux entrées pour le même ordinateur : l’entrée découverte automatiquement et l’entrée ajoutée manuellement. Pour résoudre le problème et permettre à Outlook Web App de fonctionner de nouveau, utilisez Windows PowerShell pour supprimer les entrées du pool approuvé et des applications approuvées associées au serveur. Pour plus d’informations, voir les rubriques d’aide des applets de commande <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</a> et <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</a>.

Si ces deux services s’exécutent sur des ordinateurs distincts, après avoir vérifié que le runtime Unified Communications Managed API 4.0 a été installé, vous devez créer un pool d’applications approuvées Lync Server et une application approuvée associés à Outlook Web App ; cette opération permet d’ajouter le serveur à la liste des serveurs connus. Pour ce faire, exécutez d’abord une commande semblable à ce qui suit à partir de Lync Server Management Shell :

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

Dans la commande précédente, atl-owa-001.litwareinc.com est le nom de domaine complet du pool Outlook Web App. Il doit s’agir du même nom que celui qui apparaît dans les champs du nom d’objet et de l’autre nom de sujet du certificat qui donne accès à Outlook Web App. De même, atl-cs-001.litwareinc.com est le nom de domaine complet du pool Lync Server 2013 qui doit héberger le nouveau pool d’applications approuvées. Notez également que le site spécifié, Redmond, représente le SiteID du site Lync Server. Le SiteID n’est pas nécessairement identique au DisplayName du site. Vous pouvez récupérer des SiteID pour vos sites Lync Server en exécutant la commande suivante à partir de Lync Server Management Shell :

    Get-CsSite | Select-Object DisplayName, SiteID

Après avoir créé le pool d’applications approuvées, utilisez une commande semblable à ce qui suit pour configurer une identité d’application et un port pour Outlook Web App :

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

Dans la commande précédente, ApplicationID est simplement un identificateur convivial utilisé pour différencier les applications approuvées. ApplicationID peut être une chaîne de texte qui ne contient pas d’espaces vides ou autres caractères interdits. (Pour être assuré de créer un identificateur valide, nous vous recommandons d’utiliser uniquement des lettres et des nombres quand vous spécifiez ApplicationID.) La valeur affectée au paramètre Port est également laissée à la discrétion de l’administrateur : il peut s’agir de n’importe quel port réseau disponible.

Après avoir créé une application approuvée, vous devez exécuter la commande suivante afin d’activer les modifications apportées à votre topologie Lync Server :

    Enable-CsTopology

Notez que vous devez également ajouter vos serveur de boîtes aux lettres et accès client Exchange à tous vos plans de numérotation Uri SIP. Cela permet de configurer les serveurs en tant qu’homologues SIP approuvés avec la topologie ExUmRouting pour Lync Server.

**Activation de la messagerie instantanée sur Outlook Web App**

Une fois Lync Server correctement configuré, vous pouvez commencer à configurer Outlook Web App. La première étape de ce processus consiste à activer la messagerie instantanée pour tous vos annuaires virtuels Outlook Web App sur vos serveurs frontaux. (Vous n’avez pas besoin d’activer la messagerie instantanée pour les annuaires virtuels sur vos serveurs principaux ; en fait, nous vous déconseillons de le faire.) Vous pouvez activer la messagerie instantanée sur les serveurs d’accès client en exécutant la commande suivante à partir de l’environnement de ligne de commande Exchange Management Shell :

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

> [!NOTE]  
> Par défaut, la messagerie instantanée est activée quand vous installez Outlook Web App ; en d’autres termes, la propriété InstantMessagingEnabled est définie sur True. Toutefois, vous devez exécuter la commande précédente pour définir le type de messagerie instantanée sur OCS. Par défaut, la propriété InstantMessagingType est définie sur None.

Vous devez ensuite ajouter les deux lignes suivantes au fichier Web.config d’Outlook Web App (ce fichier se trouve généralement dans le dossier C:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa). Ces deux lignes doivent être ajoutées sous le nœud \<AppSettings\> dans le fichier Web.config, et cette procédure ne doit être effectuée que sur les serveurs principaux sur lesquels Outlook Web App a été installé :

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

Dans l’exemple précédent, la valeur correspondant à IMCertificateThumbprint doit représenter l’empreinte numérique (Thumbprint) du certificat Exchange 2013 installé sur vos serveurs principaux. Vous pouvez récupérer cette information en exécutant la commande suivante à partir de l’environnement de ligne de commande Exchange Management Shell :

    Get-ExchangeCertificate

Notez également que la valeur affectée à IMServerName est le nom de domaine complet du pool Lync Server où vous avez créé le pool d’applications approuvées pour Outlook Web App.

Le certificat que vous utilisez pour Outlook Web App doit être un certificat approuvé par Lync Server. Vous pouvez vous assurer que le certificat sera approuvé à la fois par Lync Server et par Exchange en utilisant votre autorité de certification interne pour créer un certificat sur le serveur de boîtes aux lettres, afin que le nom de domaine complet du serveur soit utilisé pour le nom de l’objet et que ce nom de domaine complet apparaisse dans le champ de l’autre nom de certificat. Une fois créé, le certificat peut être importé vers les serveurs principaux. Au bout du compte, le même certificat est utilisé à une double fin : 1) pour la communication entre la messagerie unifiée Exchange et Lync Server et, 2) pour l’intégration entre Outlook Web App et Lync Server.

Après avoir mis à jour le fichier Web.config, vous devez exécuter la commande suivante sur le serveur principal Exchange afin de recycler le pool Outlook Web App :

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

Si l’opération de recyclage réussit, vous voyez le message suivant s’afficher dans l’environnement de ligne de commande Exchange Management Shell :

    "MSExchangeOWAAppPool" successfully recycled

**Configuration des stratégies de boîte aux lettres Outlook Web App**

À ce stade, vous pouvez utiliser la commande suivante afin de configurer la messagerie instantanée pour la ou les stratégies de boîte aux lettres Outlook Web App appropriées. Par exemple, cette commande, exécutée sur l’un de vos serveurs de boîtes aux lettres, active la messagerie instantanée pour la stratégie Default :

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Quant à cette commande, elle active la messagerie instantanée pour toutes vos stratégies de boîte aux lettres Outlook Web App :

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Une fois la stratégie de boîte aux lettres activée, tous les utilisateurs gérés par cette stratégie disposent d’une intégration complète entre Lync Server et Outlook Web App, à condition que :

  - l’utilisateur possède une boîte aux lettres sur Exchange 2013 ;

  - Lync Server 2013 ait été activé pour l’utilisateur ;

  - l’utilisateur possède une adresse proxy SIP valide.

**Désactivation de la messagerie instantanée dans Outlook Web App**

Comme indiqué précédemment, la messagerie instantanée est activée par défaut dans Outlook Web App. Cela signifie que si vous n’intégrez pas Outlook Web App à Lync Server, les utilisateurs verront des icônes de présence vides et un message d’erreur chaque fois qu’ils ouvriront une session sous Outlook Web App. Pour éviter ce problème, désactivez la messagerie instantanée dans Outlook web App à l’aide de la commande Exchange Management Shell suivante :

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Vérification de l’intégration à Outlook Web App**

Pour vérifier si les fonctionnalités de messagerie instantanée et de présence ont été intégrées à Outlook Web App, authentifiez-vous dans Outlook Web App 2013. Dans le coin supérieur droit de l’écran, vous voyez votre nom d’affichage Exchange. S’il existe une icône de présence à côté de votre nom (par exemple, une icône verte indiquant que votre statut actuel est Disponible), cela indique que vous avez correctement intégré Lync Server et Outlook Web App.

Après vous être authentifié dans Outlook Web App, vérifiez si un événement portant l’ID d’événement 112 (et la source MSExchange OWA) a été écrit dans le journal des événements sur le serveur de boîtes aux lettres. Cet événement indique que le gestionnaire de points de terminaison de la messagerie instantanée a été correctement initialisé. Si la messagerie instantanée ne semble pas fonctionner, sur le serveur de boîtes aux lettres, recherchez les fichiers journaux dans le dossier C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging. Si le dossier Logging ou InstantMessaging n’existe pas, cela indique que l’intégration a échoué. Dans ce cas, vous pouvez utiliser le suivi SIPStack sur Lync Server (sur l’ensemble des niveaux et des indicateurs) pour essayer de déterminer la raison de l’échec de l’intégration.

