---
title: Installer et configurer des nœuds observateur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 'Résumé : installez et configurez les nœuds observateur pour les transactions synthétiques de Skype entreprise Server.'
ms.openlocfilehash: 8efe291f72312b7634ae644d0e910cf58951b7a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/19/2020
ms.locfileid: "48599697"
---
# <a name="install-and-configure-watcher-nodes"></a>Installer et configurer des nœuds observateur
 
**Résumé :** Installez et configurez les nœuds observateur pour les transactions synthétiques de Skype entreprise Server.
  
Les nœuds observateurs sont des ordinateurs qui exécutent régulièrement des transactions synthétiques Skype entreprise Server. Les transactions synthétiques sont des applets de commande Windows PowerShell qui vérifient que les scénarios utilisateur clés, tels que la possibilité de se connecter ou d’échanger des messages instantanés, fonctionnent comme prévu. Pour Skype entreprise Server 2015, System Center Operations Manager peut exécuter les transactions synthétiques indiquées dans le tableau suivant, qui inclut trois types de transaction synthétique :
  
- **Par défaut** Transactions synthétiques qu’un nœud observateur exécute par défaut. Lorsque vous créez un nœud observateur, vous pouvez spécifier les transactions synthétiques qui seront exécutées par ce nœud. (Il s’agit de l’objectif du paramètre tests utilisé par l’applet de commande New-CsWatcherNodeConfiguration.) Si vous n’utilisez pas le paramètre tests lors de la création du nœud observateur, il exécutera automatiquement toutes les transactions synthétiques par défaut et n’exécutera aucune des transactions synthétiques non par défaut. Cela signifie, par exemple, que le nœud observateur est configuré pour exécuter le test Test-CsAddressBookService, mais qu’il ne sera pas configuré pour exécuter le test Test-CsExumConnectivity.
    
- **Non défini par défaut** Tests que les nœuds observateurs ne s’exécutent pas par défaut. (Pour plus d’informations, consultez la description du type par défaut.) Toutefois, le nœud observateur peut être activé pour exécuter les transactions synthétiques non par défaut. Vous pouvez effectuer cette opération lorsque vous créez le nœud observateur (à l’aide de l’applet de commande New-CsWatcherNodeConfiguration) ou à tout moment après la création du nœud observateur. Notez que de nombreuses transactions synthétiques non par défaut nécessitent des étapes de configuration supplémentaires. Pour plus d’informations sur ces étapes, consultez la rubrique [instructions de configuration spéciales pour les transactions synthétiques](test-users-and-settings.md#special_synthetictrans).
    
- **Étendue** Type spécial de transaction synthétique non définie par défaut. Contrairement à d’autres transactions synthétiques, les tests étendus peuvent être exécutés plusieurs fois à chaque passage. Cela est utile lors de la vérification du comportement, comme les itinéraires de communications vocales RTC (réseau téléphonique commuté) pour un pool. Vous pouvez configurer cette configuration simplement en ajoutant plusieurs instances d’un test étendu à un nœud observateur.
    
Pour plus d’informations sur le processus d’ajout d’autres transactions synthétiques à un nœud observateur, reportez-vous à la rubrique [Configure a Watcher node to Run synthetique transactions](watcher-nodes.md#enable_synthetic_trans). Vous pouvez également utiliser Skype entreprise Server Management Shell pour supprimer des transactions synthétiques d’un nœud observateur.
  
Parmi les transactions synthétiques accessibles aux nœuds observateur, citons les suivantes :
  
|**Nom de l’applet de commande (nom du test)**|**Description**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Confirme que les utilisateurs peuvent rechercher des utilisateurs qui ne figurent pas dans leur liste de contacts.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Confirme que les utilisateurs peuvent rechercher des utilisateurs qui ne figurent pas dans leur liste de contacts via HTTP.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Confirme que les utilisateurs peuvent créer des conférences audio/vidéo et participer à celles-ci.  <br/> |
|Test-CsGroupIM (Conférence par messagerie instantanée)  <br/> |Confirme que les utilisateurs peuvent envoyer des messages instantanés dans des conférences et participer à des conversations par messagerie instantanée comptant trois personnes ou plus.  <br/> |
|Test-CsIM (MESSAGERIE INSTANTANÉE P2P)  <br/> |Confirme que les utilisateurs peuvent envoyer des messages instantanés d’égal à égal.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Confirme que les utilisateurs peuvent passer des appels audio d’égal à égal (signalisation uniquement).  <br/> |
|Test-CsPresence (Presence)  <br/> |Confirme que les utilisateurs peuvent afficher la présence d’autres utilisateurs.  <br/> |
|Test-CsRegistration (Registration)  <br/> |Confirme que les utilisateurs peuvent se connecter à Skype entreprise.  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |Confirme que les utilisateurs peuvent passer des appels à des personnes à l’extérieur de l’entreprise et recevoir des appels de celles-ci (numéros PSTN).  <br/> |
|Test-CsASConference (ASConference)  <br/> |Confirme que les utilisateurs peuvent créer et participer à une conférence de partage d’application.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Confirme que les serveurs Edge de vidéo audio sont en mesure d’accepter des connexions pour les appels d’égal à égal et les téléconférences.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Confirme que les utilisateurs peuvent participer à une conférence de collaboration de données (une réunion en ligne qui inclut des activités telles que des tableaux blancs et des sondages).  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirme que les utilisateurs peuvent composer des numéros de téléphone pour participer à des conférences.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirme que les utilisateurs peuvent composer des numéros de téléphone pour participer à des conférences.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Confirme qu’un utilisateur peut se connecter à la messagerie unifiée Exchange.  <br/> |
|Test-CsGroupIM-TestJoinLauncher (JoinLauncher)  <br/> |Confirme que les utilisateurs peuvent créer et rejoindre des réunions planifiées (par le biais d’un lien d’adresse Web).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Confirme que les utilisateurs d’appareil mobile peuvent inscrire et envoyer des messages instantanés.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Confirme que le serveur d’interopérabilité vidéo fonctionne et peut gérer les connexions entrantes sur une jonction SIP vidéo.  <br/> **Remarque :** La prise en charge d’MCX pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Confirme que les utilisateurs peuvent échanger des messages à l’aide du service de conversation permanente.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Confirme que les utilisateurs peuvent participer à des conférences via le Web.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Confirme que les contacts d’un utilisateur sont accessibles via le magasin de contacts unifié. Le magasin de contacts unifié permet aux utilisateurs de conserver un seul ensemble de contacts accessible via Skype entreprise Server 2015, Outlook Messaging and collaboration client et/ou Outlook Web Access.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Confirme qu’un message instantané peut être envoyé par le biais de la passerelle XMPP (extensible Messaging and Presence Protocol).  <br/> Les passerelles XMPP et les proxys sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019.  |

Vous n’avez pas besoin d’installer les nœuds observateur pour utiliser System Center Operations Manager. Si vous n’installez pas ces nœuds, vous pouvez toujours obtenir des alertes en temps réel à partir des composants de Skype entreprise Server 2015 chaque fois qu’un problème se produit. (Le pack d’administration des composants et des utilisateurs n’utilise pas de nœuds observateur.) Toutefois, les nœuds observateurs sont requis si vous souhaitez surveiller des scénarios de bout en bout à l’aide du pack d’administration actif.
  
> [!NOTE]
> Les administrateurs peuvent également exécuter les transactions synthétiques manuellement, sans utiliser ni installer Operations Manager. En fonction de la taille de votre déploiement de Skype entreprise Server, les transactions synthétiques peuvent utiliser une grande quantité de mémoire et de temps processeur. Pour cette raison, nous vous recommandons d’utiliser un ordinateur dédié comme nœud observateur. Par exemple, vous ne devez pas configurer de serveur frontal Skype entreprise Server pour qu’il serve de nœud observateur. Les nœuds observateurs doivent respecter les mêmes exigences matérielles de base que n’importe quel autre ordinateur de votre topologie Skype entreprise Server. 
  
> [!NOTE]
> Un nœud observateur Lync Server 2013 hérité ne peut pas être colocalisé sur le même ordinateur que le nœud observateur Skype entreprise Server 2015 car les fichiers système principaux de Lync Server 2013 et Skype entreprise Server 2015 ne peuvent pas être installés sur le même ordinateur. Toutefois, les nœuds observateurs de Skype entreprise Server 2015 peuvent surveiller simultanément Skype entreprise Server 2015 et Lync Server 2013. Les transactions synthétiques par défaut sont prises en charge pour les deux versions de produit. 
  
Les nœuds observateur de Lync Server 2013 peuvent être déployés à l’intérieur ou à l’extérieur d’une entreprise pour vérifier les éléments suivants :
  
- Connectivité aux pools pour les utilisateurs au sein de l’entreprise
    
- Connectivité via les réseaux de périmètre pour les utilisateurs distants travaillant à l’extérieur de l’entreprise.
    
- Connectivité aux Branch Office Appliances
    
- Connectivité à Lync Server 2013 au sein de l’entreprise et via les réseaux de périmètre.
    
Pour simplifier l’administration, différentes options d’authentification sont disponibles pour l’intérieur et l’extérieur de l’entreprise. Pour plus d’informations, consultez [la rubrique Configuration d’un nœud observateur pour exécuter des transactions synthétiques](watcher-nodes.md#enable_synthetic_trans).
  
Pour configurer un ordinateur en tant que nœud observateur, vous devez d’abord effectuer les conditions préalables suivantes : 
  
- Installez System Center Operations Manager et importez les packs d’administration de Skype entreprise Server 2015. Vous devez également vérifier que l’ordinateur du nœud observateur remplit toutes les conditions préalables à l’installation de Skype entreprise Server 2015.
    
- Installez les éléments suivants sur l’ordinateur du nœud observateur :
    
  - Version complète de .NET Framework 4,5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Une fois que les conditions préalables sont remplies, vous pouvez configurer le nœud observateur en procédant comme suit :
  
1. Installez les fichiers principaux de Skype entreprise Server 2015 sur l’ordinateur du nœud observateur.
    
2. Installez l’agent System Center Operations Manager sur l’ordinateur du nœud observateur.
    
3. Exécutez le fichier exécutable de la Watchernode.msi.
    
4. Utilisez la cmdlet **New-applet cswatchernodeconfiguration** pour configurer les comptes d’utilisateurs test devant être utilisés par le nœud observateur.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Installer les fichiers principaux de Skype entreprise Server 2015 et la base de données RTCLocal

Pour installer les fichiers principaux de Skype entreprise Server 2015 sur un ordinateur, procédez comme suit. La base de données RTCLocal est installée automatiquement lorsque vous installez les fichiers principaux. Notez que vous n’avez pas besoin d’installer SQL Server sur les nœuds observateur. SQL Server Express sera automatiquement installé.
  
Pour installer les fichiers principaux de Skype entreprise Server 2015 et la base de données RTCLocal :
  
1. Sur l’ordinateur nœud observateur, cliquez sur Démarrer, sur Tous les programmes, sur Accessoires, cliquez avec le bouton droit sur Invite de commandes, puis cliquez sur Exécuter en tant qu’administrateur.
    
2. Dans la fenêtre de la console, tapez la commande suivante, puis appuyez sur entrée. Veillez à entrer le chemin d’accès approprié à vos fichiers d’installation de Skype entreprise Server : D:\Setup.exe/BootstrapLocalMgmtTo Vérifiez que les composants de base de Skype entreprise Server sont correctement installés, cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Skype entreprise Server Management Shell**. Dans Skype entreprise Server Management Shell, tapez la commande Windows PowerShell suivante et appuyez sur entrée :
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> La première fois que vous exécutez cette commande, aucune donnée n’est renvoyée car vous n’avez pas encore configuré de nœuds observateur. Si la commande s’exécute sans renvoyer d’erreur, vous pouvez supposer que l’installation de Skype entreprise Server a réussi. 
  
Si votre ordinateur nœud observateur se trouve à l’intérieur de votre réseau de périmètre, vous pouvez exécuter la commande suivante pour vérifier l’installation de Skype entreprise Server 2015 :
  
Get-CsPinPolicyYou recevront des informations similaires à celles-ci, en fonction du nombre de stratégies de code confidentiel configurées pour être utilisées dans votre organisation :
  
Identity : global
  
Description
  
MinPasswordLength : 5
  
PINHistoryCount : 0
  
AllowCommonPatterns : false
  
PINLifetime : 0
  
MaximumLogonAttempts :
  
Si vous voyez des informations sur vos stratégies de code confidentiel, les composants principaux ont été correctement installés.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Installer les fichiers de l’agent Operation Manager sur un nœud observateur

De la même manière que pour le programme d’installation de Skype entreprise Server pour les alertes de composant de création de rapports, un nœud observateur de Skype entreprise Server 2015 nécessite l’installation des fichiers de l’agent System Center Operations Manager. Cela permet d’exécuter les transactions synthétiques et d’indiquer des alertes au serveur d’administration racine System Center Operations Manager.
  
Pour installer les fichiers de l’agent, suivez les procédures indiquées dans [configure the Skype for Business Server Computers that be monitored](configure-computers-to-monitor.md).
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Configuration d’un nœud observateur pour exécuter des transactions synthétiques
<a name="enable_synthetic_trans"> </a>

Une fois que les fichiers de l’agent System Center Operations Manager ont été installés, vous devez configurer le nœud observateur lui-même. Les étapes à suivre pour effectuer cette opération varient selon que votre ordinateur de nœud observateur se trouve à l’intérieur de votre réseau de périmètre ou à l’extérieur de votre réseau de périmètre. 
  
Lorsque vous configurez un nœud observateur, vous devez également choisir le type de méthode d’authentification utilisé par ce nœud. Skype entreprise Server 2015 vous permet de choisir l’une des deux méthodes d’authentification : serveur approuvé ou authentification des informations d’identification. Le tableau suivant présente les différences entre ces deux méthodes :
  
||**Description**|**Emplacements pris en charge**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Utilise un certificat pour emprunter l’identité d’un serveur interne et contourner les demandes d’authentification.  <br/> Utile pour les administrateurs qui préfèrent gérer un seul certificat, au lieu de plusieurs mots de passe d’utilisateur sur chaque nœud observateur.  <br/> |Au sein de l’entreprise.  <br/> Avec cette méthode, le nœud observateur doit se trouver dans le même domaine que les pools surveillés. Si le nœud observateur et les pools se trouvent dans des domaines différents, utilisez plutôt l’authentification des informations d’identification.  <br/> |
|Poursuivre  <br/> |Stocke les noms d’utilisateur et mots de passe de manière sécurisée dans le Gestionnaire d’informations d’identification Windows sur chaque nœud observateur.  <br/> Ce mode nécessite davantage de gestion des mots de passe, mais est la seule option pour les nœuds observateur à l’extérieur de l’entreprise. Ces nœuds observateurs ne peuvent pas être traités comme un point de terminaison approuvé pour l’authentification.  <br/> |En dehors de l’entreprise.  <br/> Au sein de l’entreprise.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Configuration d’un nœud observateur pour utiliser l’authentification de serveur approuvé
<a name="enable_synthetic_trans"> </a>

Si l’ordinateur du nœud observateur se trouve à l’intérieur du réseau de périmètre, l’utilisation de l’authentification de serveur approuvée peut considérablement réduire les tâches d’administration en conservant un seul certificat, au lieu d’utiliser un grand nombre de mots de passe de compte d’utilisateur.
  
Pour configurer l’authentification de serveur approuvé, vous devez d’abord créer un pool d’applications approuvées pour héberger l’ordinateur du nœud observateur. Une fois que vous avez créé le pool d’applications approuvées, vous devez configurer les transactions synthétiques sur le nœud observateur pour qu’elles s’exécutent en tant qu’applications approuvées.
  
> [!NOTE]
> Une application approuvée est une application dotée d’un État approuvé à exécuter dans le cadre de Skype entreprise Server 2015, mais qui n’est pas intégré au produit. Le statut d’application approuvée signifie que l’application n’a pas à s’authentifier chaque fois qu’elle s’exécute.
  
Pour créer un pool d’applications approuvées, ouvrez Skype entreprise Server Management Shell et exécutez une commande semblable à celle-ci :
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Pour plus d’informations sur les paramètres de la commande précédente, tapez ce qui suit à partir de l’invite Skype entreprise Server Management Shell : 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

Après avoir créé le pool d’applications approuvées, vous pouvez configurer l’ordinateur du nœud observateur pour qu’il exécute les transactions synthétiques en tant qu’application approuvée à l’aide de la cmdlet **New-CsTrustedApplication** et d’une commande semblable à celle-ci :
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Une fois que cette commande est terminée et que l’application approuvée est créée, vous devez exécuter la cmdlet **Enable-CsTopology** pour vous assurer que les modifications prennent effet :
  
```PowerShell
Enable-CsTopology
```

Le compte d’ordinateur du nœud observateur doit pouvoir interroger CMS pour certaines transactions synthétiques. Pour autoriser cette fonctionnalité, ajoutez le compte d’ordinateur du nœud observateur au groupe de sécurité RTCUniversalReadOnlyAdmins. Une fois la réplication Active Directory effectuée, redémarrez l’ordinateur.
  
Pour vérifier que la nouvelle application approuvée a été créée, tapez ce qui suit à l’invite Skype entreprise Server Management Shell :
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Configurer un certificat par défaut sur le nœud observateur
<a name="enable_synthetic_trans"> </a>

Chaque nœud observateur qui utilise l’authentification TrustedServer doit avoir un certificat par défaut affecté à l’aide de l’Assistant Déploiement de Skype entreprise Server. 
  
Pour affecter un certificat par défaut :
  
1. Cliquez sur Démarrer, sur tous les programmes, sur Skype entreprise Server 2015, puis sur Assistant Déploiement de Skype entreprise Server. 
    
2. Dans l’Assistant Déploiement de Skype entreprise Server, cliquez sur installer ou mettre à jour le système Skype entreprise Server, puis cliquez sur exécuter sous le titre demander, installer ou assigner un certificat. 
    
> [!NOTE]
> Si le bouton Exécuter est désactivé, vous devrez peut-être d’abord cliquer sur Exécuter sous Installer le magasin de configurations local. 
  
Effectuez l'une des opérations suivantes :
  
- Si vous disposez déjà d’un certificat qui peut être utilisé comme certificat par défaut, cliquez sur par défaut dans l’Assistant certificat, puis cliquez sur affecter. Suivez les étapes de l’Assistant permettant d’affecter un certificat pour affecter ce certificat.
    
- Si vous devez demander un certificat pour utiliser le certificat par défaut, cliquez sur demander, puis suivez les étapes de l’Assistant demande de certificat pour demander ce certificat. Si vous utilisez les valeurs par défaut pour le certificat de serveur web, vous obtenez un certificat que vous pouvez affecter en tant que certificat par défaut.
    
## <a name="install-and-configure-a-watcher-node"></a>Installer et configurer un nœud observateur
<a name="enable_synthetic_trans"> </a>

Une fois que vous avez redémarré l’ordinateur du nœud observateur et que vous avez configuré un certificat, vous devez exécuter le fichier Watchernode.msi. (Vous devez exécuter Watchernode.msi sur n’importe quel ordinateur où les composants principaux des fichiers de l’agent Operations Manager et de Skype entreprise Server 2015 sont installés.) 
  
Pour installer et configurer un nœud observateur :
  
1. Ouvrez Skype entreprise Server Management Shell en cliquant sur Démarrer, sur tous les programmes, sur Skype entreprise Server 2015, puis sur Skype entreprise Server Management Shell. 
    
2. Dans Management Shell, tapez la commande suivante, puis appuyez sur entrée (Assurez-vous et spécifiez le chemin d’accès réel à votre copie de Watchernode.msi) :
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> Vous pouvez également exécuter Watchernode.msi n à partir d’une fenêtre de commande. Pour ouvrir une fenêtre de commande, cliquez sur Démarrer, cliquez avec le bouton droit sur Invite de commandes, puis cliquez sur Exécuter en tant qu’administrateur. Lorsque la fenêtre de commande s’ouvre, tapez la commande illustrée à l’étape 2 ci-dessus. 
  
> [!IMPORTANT]
> Dans la commande précédente, la paire nom/valeur Authentication = TrustedServer est sensible à la casse. Il doit être tapé exactement comme indiqué. Par exemple, cette commande échoue car elle n’utilise pas la casse appropriée : 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

Le mode TrustedServer ne peut être utilisé qu’avec des ordinateurs se trouvant dans le réseau de périmètre. Lorsqu’un nœud observateur s’exécute en mode TrustedServer, les administrateurs n’ont pas besoin de gérer les mots de passe des utilisateurs test sur l’ordinateur.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Configuration d’un nœud observateur pour l’utilisation de Negotiate
<a name="enable_synthetic_trans"> </a>

Si votre ordinateur nœud observateur se trouve en dehors du réseau de périmètre, vous devez suivre une procédure légèrement différente afin de configurer ce nœud observateur afin qu’il exécute des transactions synthétiques : en particulier, vous ne devez pas créer un pool d’applications approuvées ou une application approuvée. Cela signifie que vous devrez effectuer les deux tâches suivantes.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Mettre à jour l’appartenance au groupe RTC local Read-Only administrateurs

Si votre nœud observateur se trouve en dehors du réseau de périmètre, vous devez ajouter le compte de service réseau au groupe RTC local Read-Only Administrators sur l’ordinateur du nœud observateur en effectuant la procédure suivante sur le nœud observateur :
  
1. Cliquez sur Démarrer, cliquez avec le bouton droit sur Ordinateur et cliquez sur Gérer.
    
2. Dans le Gestionnaire de serveur, développez Configuration et Utilisateurs et groupes locaux, puis cliquez sur Groupes.
    
3. Dans le volet Groupes, double-cliquez sur RTC Local Read-only Administrators.
    
4. Dans la boîte de dialogue RTC Local Read-only Administrators - Propriétés, cliquez sur Ajouter.
    
5. Dans la boîte de dialogue Sélectionner des utilisateurs, des ordinateurs, des comptes de service ou des groupes, cliquez sur Emplacements.
    
6. Dans la boîte de dialogue Emplacements, sélectionnez le nom de l’ordinateur de nœud observateur, puis cliquez sur OK.
    
7. Dans la zone Entrez les noms d’objets à sélectionner, tapez Service réseau, puis cliquez sur OK.
    
8. Dans la boîte de dialogue RTC Local Read-only Administrators - Propriétés, cliquez sur OK, puis fermez le Gestionnaire de serveur.
    
9. Redémarrez l’ordinateur de nœud observateur.
    
### <a name="install-the-watcher-node-configuration-files"></a>Installer les fichiers de configuration du nœud observateur

L’étape suivante consiste à exécuter le Watchernode.msi de fichiers : 
  
1. Ouvrez Microsoft Skype entreprise Server 2015 Management Shell. Cliquez sur Démarrer, sur tous les programmes, sur Microsoft Skype entreprise Server 2015, puis sur Skype entreprise Server Management Shell. 
    
2. Dans Skype entreprise Server Management Shell, tapez la commande suivante, puis appuyez sur entrée (veillez à spécifier le chemin d’accès réel à votre copie de Watchernode.msi) :
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Comme mentionné précédemment, Watchernode.msi peut également être exécuté à partir d’une fenêtre de commande. Pour ouvrir une fenêtre de commande, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**. Lorsque la fenêtre de commande s’ouvre, tapez la commande illustrée à l’étape 2 ci-dessus. 
  
Le mode Négocier est utilisé à chaque fois que le nœud observateur ne peut pas être configuré en tant que pool d’application approuvées. Dans ce mode, les administrateurs devront gérer les mots de passe des utilisateurs de test sur le nœud observateur.
  

