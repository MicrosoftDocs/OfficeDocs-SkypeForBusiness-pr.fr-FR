---
title: Comment installer et configurer des nodes d’observation
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: Décrit le processus d’installation et de configuration des nodes d’Skype Entreprise Server transactions synthétiques.
ms.openlocfilehash: 34ab33bb486e3bc9973632c108e6eccf33bec481
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396677"
---
# <a name="learn-to-install-configure-watcher-nodes"></a>Découvrez comment installer, configurer des nodes d’observation
 
**Résumé :** Installez et configurez des nodes d’Skype Entreprise Server pour les transactions synthétiques.
  
Les nodes observeur sont des ordinateurs qui exécutent régulièrement Skype Entreprise Server transactions synthétiques. Les transactions synthétiques sont Windows PowerShell cmdlets qui vérifient que les scénarios utilisateur clés, tels que la possibilité de se connecter ou d’échanger des messages instantanés, fonctionnent comme prévu. Pour Skype Entreprise Server 2015, System Center Operations Manager peut exécuter les transactions synthétiques indiquées dans le tableau suivant, qui inclut trois types de transaction synthétique :
  
- **Valeur par défaut** Transactions synthétiques qu’un nœud d’observation exécute par défaut. Lorsque vous créez un nœud d’observation, vous pouvez spécifier les transactions synthétiques qui s’exécuteront. (C’est l’objectif du paramètre Tests utilisé par l'New-CsWatcherNodeConfiguration cmdlet.) Si vous n’utilisez pas le paramètre Tests lors de la création du nœud observeur, il exécute automatiquement toutes les transactions synthétiques par défaut et n’exécute aucune des transactions synthétiques non par défaut. Cela signifie, par exemple, que le nœud de l'Test-CsAddressBookService sera configuré pour exécuter le test Test-CsAddressBookService, mais pas pour exécuter le test Test-CsExumConnectivity test.
    
- **Non par défaut** Teste que les nodes de l’observeur ne s’exécutent pas par défaut. (Pour plus d’informations, voir la description du type Par défaut.) Toutefois, le nœud de l’observation peut être activé pour exécuter l’une des transactions synthétiques autres que les transactions synthétiques par défaut. Vous pouvez le faire lorsque vous créez le nœud de l’observation (à l’aide de l'New-CsWatcherNodeConfiguration cmdlet) ou à tout moment après la création du nœud. Notez que de nombreuses transactions synthétiques non par défaut nécessitent des étapes de configuration supplémentaires. Pour plus d’informations sur ces étapes, voir [Special Setup Instructions for Synthetic Transactions](test-users-and-settings.md#special_synthetictrans).
    
- **Étendue** Type spécial de transaction synthétique non par défaut. Contrairement à d’autres transactions synthétiques, les tests étendus peuvent être exécutés plusieurs fois à chaque passage. Cela est utile lors de la vérification du comportement, par exemple, plusieurs itinéraires de communications vocales PSTN (réseau téléphonique commuté) pour un pool. Vous pouvez configurer cela simplement en ajoutant plusieurs instances d’un test étendu à un nœud de l’analyseur.
    
Pour plus d’informations sur le processus d’ajout d’autres transactions synthétiques à un nœud de l’analyseur, voir [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans). Vous pouvez également utiliser Skype Entreprise Server Management Shell pour supprimer des transactions synthétiques d’un nœud d’observation.
  
Parmi les transactions synthétiques accessibles aux nœuds observateur, citons les suivantes :
  
|**Nom de l’applet de commande (nom du test)**|**Description**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Confirme que les utilisateurs peuvent rechercher des utilisateurs qui ne sont pas dans leur liste de contacts.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Confirme que les utilisateurs peuvent rechercher des utilisateurs qui ne sont pas dans leur liste de contacts via HTTP.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Confirme que les utilisateurs peuvent créer des conférences audio/vidéo et participer à celles-ci.  <br/> |
|Test-CsGroupIM (conférence de messagerie instantanée)  <br/> |Confirme que les utilisateurs peuvent envoyer des messages instantanés dans des conférences et participer à des conversations par messagerie instantanée comptant trois personnes ou plus.  <br/> |
|Test-CsIM (messagerie instantanée P2P)  <br/> |Confirme que les utilisateurs peuvent envoyer des messages instantanés d’égal à égal.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Confirme que les utilisateurs peuvent passer des appels audio d’égal à égal (signalisation uniquement).  <br/> |
|Test-CsPresence (Presence)  <br/> |Confirme que les utilisateurs sont en mesure d’afficher la présence d’autres utilisateurs.  <br/> |
|Test-CsRegistration (Registration)  <br/> |Confirme que les utilisateurs peuvent se Skype Entreprise.  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |Confirme que les utilisateurs peuvent passer des appels à des personnes à l’extérieur de l’entreprise et recevoir des appels de celles-ci (numéros PSTN).  <br/> |
|Test-CsASConference (ASConference)  <br/> |Confirme que les utilisateurs peuvent créer et participer à une conférence de partage d’application.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Confirme que les serveurs Edge audio vidéo sont en mesure d’accepter les connexions pour les appels d’égal à égal et les appels de conférence.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Confirme que les utilisateurs peuvent participer à une conférence de collaboration de données (une réunion en ligne qui inclut des activités telles que des tableaux blancs et des sondages).  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirme que les utilisateurs peuvent composer des numéros de téléphone pour participer à des conférences.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirme que les utilisateurs peuvent composer des numéros de téléphone pour participer à des conférences.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Confirme qu’un utilisateur peut se connecter à Exchange messagerie unifiée.  <br/> |
|Test-CsGroupIM -TestJoinLauncher (JoinLauncher)  <br/> |Confirme que les utilisateurs sont en mesure de créer et de participer à des réunions programmées (par un lien d’adresse web).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Confirme que les utilisateurs d’appareil mobile peuvent inscrire et envoyer des messages instantanés.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Confirme que le serveur d’interopation vidéo est en cours et peut gérer les connexions entrantes sur une connexion SIP vidéo.  <br/> **Remarque :** La prise en charge de MCX pour les clients mobiles hérités n’est plus disponible Skype Entreprise Server 2019. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Confirme que les utilisateurs peuvent échanger des messages à l’aide du service de conversation permanente.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Confirme que les utilisateurs peuvent participer à des conférences via le web.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Confirme que les contacts d’un utilisateur sont accessibles via le magasin de contacts unifié. Le magasin de contacts unifié permet aux utilisateurs de gérer un ensemble unique de contacts accessibles à l’aide de Skype Entreprise Server 2015, du client de messagerie et de collaboration Outlook et/ou de Outlook Web Access.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Confirme qu’un message instantané peut être envoyé sur la passerelle XMPP (Extensible Messaging and Presence Protocol).  <br/> Les passerelles et les proxies XMPP sont disponibles dans Skype Entreprise Server 2015, mais ne sont plus pris en charge dans Skype Entreprise Server 2019.  |

Vous n’avez pas besoin d’installer des nodes d’observation pour utiliser System Center Operations Manager. Si vous n’installez pas ces derniers, vous pouvez toujours obtenir des alertes en temps réel à partir de Skype Entreprise Server 2015 chaque fois qu’un problème se produit. (Le pack d’administration des composants et des utilisateurs n’utilise pas de nodes d’observation.) Toutefois, les nodes observateurs sont requis si vous souhaitez surveiller les scénarios de bout en bout à l’aide du pack d’administration Active Monitoring.
  
> [!NOTE]
> Les administrateurs peuvent également exécuter des transactions synthétiques manuellement, sans utiliser ou installer Operations Manager. Selon la taille de votre déploiement Skype Entreprise Server, les transactions synthétiques peuvent utiliser une grande quantité de mémoire ordinateur et de temps processeur. Pour cette raison, nous vous recommandons d’utiliser un ordinateur dédié comme nœud d’observation. Par exemple, vous ne devez pas configurer un serveur Skype Entreprise Server frontal pour qu’il agisse en tant que nœud d’observation. Les nodes de l’observeur doivent respecter la même configuration matérielle de base que tout autre ordinateur de votre topologie Skype Entreprise Server de base. 
  
> [!NOTE]
> Un nœud d’observation Lync Server 2013 hérité ne peut pas être coqueté sur le même ordinateur qu’un nœud d’observation Skype Entreprise Server 2015, car les fichiers système principaux pour Lync Server 2013 et Skype Entreprise Server 2015 ne peuvent pas être installés sur le même ordinateur. Toutefois, Skype Entreprise Server 2015 peuvent surveiller simultanément Skype Entreprise Server 2015 et Lync Server 2013. Les transactions synthétiques par défaut sont pris en charge pour les deux versions du produit. 
  
Les serveurs d’observation Lync Server 2013 peuvent être déployés à l’intérieur ou à l’extérieur d’une entreprise pour vous aider à vérifier :
  
- Connectivité aux pools pour les utilisateurs au sein de l’entreprise
    
- Connectivité via les réseaux de périmètre pour les utilisateurs distants travaillant en dehors de l’entreprise.
    
- Connectivité aux Branch Office Appliances
    
- Connectivité à Lync Server 2013 à l’intérieur de l’entreprise et via les réseaux de périmètre.
    
Pour simplifier l’administration, différentes options d’authentification sont disponibles à l’intérieur et à l’extérieur de l’entreprise. Pour plus d’informations, voir [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).
  
Pour configurer un ordinateur comme nœud d’observation, vous devez d’abord remplir les conditions préalables suivantes : 
  
- Installez System Center Operations Manager et importez les packs d Skype Entreprise Server 2015. Vous devez également d’abord vérifier que l’ordinateur du nœud observeur répond à toutes les conditions préalables à l’installation Skype Entreprise Server 2015.
    
- Installez les éléments suivants sur l’ordinateur du nœud de l’observeur :
    
  - Version complète de .NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Une fois que les conditions préalables sont remplies, vous pouvez configurer le nœud de l’observeur en suivant les étapes suivantes :
  
1. Installez les Skype Entreprise Server 2015 principaux sur l’ordinateur du nœud de l’observeur.
    
2. Installez System Center’agent Operations Manager sur l’ordinateur du nœud observeur.
    
3. Exécutez le Watchernode.msi exécutable.
    
4. La cmdlet **New-CsWatcherNodeConfiguration** permet de configurer les comptes d’utilisateur test à utiliser par le nœud observateur.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Installer les fichiers Skype Entreprise Server 2015 et la base de données RTCLocal

Pour installer les Skype Entreprise Server 2015 principaux sur un ordinateur, complétez la procédure suivante. La base de données RTCLocal est automatiquement installée lorsque vous installez les fichiers principaux. Notez que vous n’avez pas besoin d’installer SQL Server sur les nodes de l’observeur. SQL Server Express sera installé automatiquement.
  
Pour installer les fichiers Skype Entreprise Server 2015 et la base de données RTCLocal :
  
1. Sur l’ordinateur nœud observateur, cliquez sur Démarrer, sur Tous les programmes, sur Accessoires, cliquez avec le bouton droit sur Invite de commandes, puis cliquez sur Exécuter en tant qu’administrateur.
    
2. Dans la fenêtre de console, tapez la commande suivante et appuyez sur Entrée. N’oubliez pas d’entrer le chemin d’accès approprié à vos fichiers d’installation Skype Entreprise Server : D:\Setup.exe /BootstrapLocalMgmtTo verify that the core Skype Entreprise Server components are successfully installed, click **Start**, click **All Programs**, click **Skype Entreprise Server 2015**, puis cliquez sur **Skype Entreprise Server Management Shell**. Dans l’Skype Entreprise Server Management Shell, tapez la commande Windows PowerShell commande suivante et appuyez sur Entrée :
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> La première fois que vous exécutez cette commande, aucune donnée n’est renvoyée, car vous n’avez pas encore configuré d’ordinateurs de nœuds d’observation. Si la commande s’exécute sans renvoyer d’erreur, vous pouvez supposer que l’Skype Entreprise Server a été correctement effectuée. 
  
Si votre ordinateur de nœud observeur se trouve à l’intérieur de votre réseau de périmètre, vous pouvez exécuter la commande suivante pour vérifier l’installation de Skype Entreprise Server 2015 :
  
Get-CsPinPolicyYou recevrez des informations similaires, selon le nombre de stratégies de code confidentiel configurées pour être utilisés dans votre organisation :
  
Identité : global
  
Description :
  
MinPasswordLength : 5
  
PINHistoryCount : 0
  
AllowCommonPatterns : False
  
PINLifetime : 0
  
MaximumLogonAttempts :
  
Si vous voyez des informations sur vos stratégies de code confidentiel, les composants principaux ont été correctement installés.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Installer les fichiers de l’agent Operation Manager sur un nœud de l’observeur

À l’Skype Entreprise Server pour la signalement des alertes de composant, un nœud Skype Entreprise Server 2015 requiert l’installation System Center’agent Operations Manager. Cela permet d’exécuter les transactions synthétiques et de faire état d’alertes au serveur d’administration racine System Center Operations Manager.
  
Pour installer les fichiers de l’agent, suivez les procédures répertoriées dans [Configure the Skype Entreprise Server ordinateurs qui seront surveillés](configure-computers-to-monitor.md).
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Configurer un nœud watcher pour exécuter des transactions synthétiques
<a name="enable_synthetic_trans"> </a>

Une fois les System Center’agent Operations Manager installés, vous devez configurer le nœud de l’observeur lui-même. Les étapes à suivre pour ce faire varient, selon que votre ordinateur de nœud d’observation se trouve à l’intérieur de votre réseau de périmètre ou à l’extérieur de votre réseau de périmètre. 
  
Lorsque vous configurez un nœud observateur, vous devez également choisir le type de méthode d’authentification utilisé par ce nœud. Skype Entreprise Server 2015 vous permet de choisir l’une des deux méthodes d’authentification : serveur approuvé ou authentification des informations d’identification. Le tableau suivant présente les différences entre ces deux méthodes :
  
|&nbsp;|**Description**|**Emplacements pris en charge**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Utilise un certificat pour emprunter l’identité d’un serveur interne et contourner les demandes d’authentification.  <br/> Utile pour les administrateurs qui préfèrent gérer un certificat unique, au lieu de nombreux mots de passe utilisateur sur chaque nœud de l’utilisateur.  <br/> |Au sein de l’entreprise.  <br/> Avec cette méthode, le nœud observateur doit se trouver dans le même domaine que les pools surveillés. Si le nœud de l’observation et les pools sont dans des domaines différents, utilisez plutôt l’authentification des informations d’identification.  <br/> |
|Négocier  <br/> |Stocke les noms d’utilisateur et mots de passe de manière sécurisée dans le Gestionnaire d’informations d’identification Windows sur chaque nœud observateur.  <br/> Ce mode nécessite davantage de gestion des mots de passe, mais il s’agit de la seule option pour les nodes observeur en dehors de l’entreprise. Ces nœuds observateurs ne peuvent pas être traités comme un point de terminaison approuvé pour l’authentification.  <br/> |En dehors de l’entreprise.  <br/> Au sein de l’entreprise.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Configurer un nœud watcher pour utiliser l’authentification de serveur approuvé
<a name="enable_synthetic_trans"> </a>

Si votre ordinateur de nœud observe se trouve à l’intérieur du réseau de périmètre, l’utilisation de l’authentification de serveur approuvé peut considérablement réduire les tâches d’administration en conservant un certificat unique, plutôt que d’utiliser de nombreux mots de passe de compte d’utilisateur.
  
Pour configurer l’authentification de serveur approuvé, vous devez d’abord créer un pool d’applications de confiance pour héberger l’ordinateur du nœud de l’observeur. Une fois que vous avez créé le pool d’applications fiables, vous devez configurer les transactions synthétiques sur ce nœud pour qu’ils s’exécutent en tant qu’applications fiables.
  
> [!NOTE]
> Une application fiable est une application qui a un statut approuvé pour s’exécuter dans le cadre de Skype Entreprise Server 2015, mais qui n’est pas une partie intégrée du produit. Le statut d’application approuvée signifie que l’application n’a pas à s’authentifier chaque fois qu’elle s’exécute.
  
Pour créer un pool d’applications fiables, ouvrez Skype Entreprise Server Management Shell et exécutez une commande semblable à celle-ci :
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Pour plus d’informations sur les paramètres de la commande précédente, tapez ce qui suit à partir de l’invite Skype Entreprise Server Management Shell : 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

Après avoir créé le pool d’applications fiables, vous pouvez configurer l’ordinateur du nœud observeur pour qu’il exécute des transactions synthétiques en tant qu’application de confiance à l’aide de l';cmdlet **New-CsTrustedApplication** et d’une commande semblable à celle-ci :
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Lorsque cette commande est terminée et que l’application de confiance est créée, vous devez exécuter l’cmdlet **Enable-CsTopology** pour vous assurer que les modifications prennent effet :
  
```PowerShell
Enable-CsTopology
```

Le compte d’ordinateur du nœud observeur nécessite la possibilité d’interroger CMS pour certaines transactions synthétiques. Pour autoriser cette possibilité, ajoutez le compte d’ordinateur du nœud watcher au groupe de sécurité RTCUniversalReadOnlyAdmins. Une fois la réplication AD s’est produite, redémarrez l’ordinateur.
  
Pour vérifier que la nouvelle application de confiance a été créée, tapez ce qui suit à l’invite Skype Entreprise Server Management Shell :
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Configurer un certificat par défaut sur le nœud de l’observation
<a name="enable_synthetic_trans"> </a>

Chaque nœud observateur qui utilise l’authentification TrustedServer doit avoir un certificat par défaut affecté à l’aide de l Skype Entreprise Server De déploiement. 
  
Pour affecter un certificat par défaut :
  
1. Cliquez sur Démarrer, sur Tous les programmes, Skype Entreprise Server 2015, puis sur Skype Entreprise Server Déploiement. 
    
2. Dans l’Assistant Skype Entreprise Server Déploiement, cliquez sur Installer ou mettre à jour Skype Entreprise Server système, puis cliquez sur Exécuter sous le titre Demander, installer ou attribuer un certificat. 
    
> [!NOTE]
> Si le bouton Exécuter est désactivé, vous devrez peut-être d’abord cliquer sur Exécuter sous Installer le magasin de configurations local. 
  
Effectuez l'une des opérations suivantes :
  
- Si vous avez déjà un certificat qui peut être utilisé comme certificat par défaut, cliquez sur Par défaut dans l’Assistant Certificat, puis cliquez sur Affecter. Suivez les étapes de l’Assistant permettant d’affecter un certificat pour affecter ce certificat.
    
- Si vous devez demander un certificat pour utiliser le certificat par défaut, cliquez sur Demander, puis suivez les étapes de l’Assistant Demande de certificat pour demander ce certificat. Si vous utilisez les valeurs par défaut pour le certificat de serveur web, vous obtenez un certificat que vous pouvez affecter en tant que certificat par défaut.
    
## <a name="install-and-configure-a-watcher-node"></a>Installer et configurer un nœud watcher
<a name="enable_synthetic_trans"> </a>

Après avoir redémarré l’ordinateur du nœud observeur et configuré un certificat, vous devez exécuter le fichier Watchernode.msi. (Vous devez exécuter Watchernode.msi sur n’importe quel ordinateur sur lequel les fichiers de l’agent Operations Manager et les composants principaux Skype Entreprise Server 2015 sont installés.) 
  
Pour installer et configurer un nœud d’observation :
  
1. Ouvrez Skype Entreprise Server Management Shell en cliquant sur Démarrer, sur Tous les programmes, sur Skype Entreprise Server 2015, puis sur Skype Entreprise Server Management Shell. 
    
2. Dans l’management Shell, tapez la commande suivante, puis appuyez sur Entrée (assurez-vous de spécifier le chemin d’accès réel à votre copie de Watchernode.msi) :
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> Vous pouvez également exécuter Watchernode.msi n à partir d’une fenêtre de commande. Pour ouvrir une fenêtre de commande, cliquez sur Démarrer, cliquez avec le bouton droit sur Invite de commandes, puis cliquez sur Exécuter en tant qu’administrateur. Lorsque la fenêtre de commande s’ouvre, tapez la commande indiquée à l’étape 2, ci-dessus. 
  
> [!IMPORTANT]
> Dans la commande précédente, la paire nom/valeur Authentication=TrustedServer est sensible à la cas. Il doit être tapé exactement comme indiqué. Par exemple, cette commande échoue, car elle n’utilise pas la boîte aux lettres correcte : 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

Le mode TrustedServer peut être utilisé uniquement avec les ordinateurs qui se trouvent à l’intérieur du réseau de périmètre. Lorsqu’un nœud observateur s’exécute en mode TrustedServer, les administrateurs n’ont pas besoin de gérer les mots de passe des utilisateurs de test sur l’ordinateur.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Configurer un nœud watcher pour utiliser Negotiate
<a name="enable_synthetic_trans"> </a>

Si votre ordinateur de nœud observeur se trouve en dehors du réseau de périmètre, vous devez suivre une procédure légèrement différente pour configurer ce nœud pour qu’il exécute des transactions synthétiques : en particulier, vous ne devez pas créer de pool d’applications ou d’applications fiables. Cela signifie que vous devrez effectuer les deux tâches suivantes.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Mettre à jour l’appartenance au groupe Read-Only RTC

Si votre nœud d’observation se trouve en dehors du réseau de périmètre, vous devez ajouter le compte service réseau au groupe RTC Local Read-only Administrators sur l’ordinateur du nœud de l’observation en effectuant la procédure suivante sur le nœud de l’observation :
  
1. Cliquez sur Démarrer, cliquez avec le bouton droit sur Ordinateur et cliquez sur Gérer.
    
2. Dans le Gestionnaire de serveur, développez Configuration et Utilisateurs et groupes locaux, puis cliquez sur Groupes.
    
3. Dans le volet Groupes, double-cliquez sur RTC Local Read-only Administrators.
    
4. Dans la boîte de dialogue RTC Local Read-only Administrators - Propriétés, cliquez sur Ajouter.
    
5. Dans la boîte de dialogue Sélectionner des utilisateurs, des ordinateurs, des comptes de service ou des groupes, cliquez sur Emplacements.
    
6. Dans la boîte de dialogue Emplacements, sélectionnez le nom de l’ordinateur de nœud observateur, puis cliquez sur OK.
    
7. Dans la zone Entrez les noms d’objets à sélectionner, tapez Service réseau, puis cliquez sur OK.
    
8. Dans la boîte de dialogue RTC Local Read-only Administrators - Propriétés, cliquez sur OK, puis fermez le Gestionnaire de serveur.
    
9. Redémarrez l’ordinateur de nœud observateur.
    
### <a name="install-the-watcher-node-configuration-files"></a>Installer les fichiers de configuration du nœud de l’watcher

L’étape suivante consiste à exécuter le fichier Watchernode.msi : 
  
1. Ouvrez Microsoft Skype Entreprise Server 2015 Management Shell. Cliquez sur Démarrer, sur Tous les programmes, sur Microsoft Skype Entreprise Server 2015, puis sur Skype Entreprise Server Management Shell. 
    
2. Dans Skype Entreprise Server Management Shell, tapez la commande suivante, puis appuyez sur Entrée (assurez-vous de spécifier le chemin d’accès réel à votre copie de Watchernode.msi) :
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Comme mentionné précédemment, les Watchernode.msi peuvent également être exécutés à partir d’une fenêtre de commande. Pour ouvrir une fenêtre de commande, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**. Lorsque la fenêtre de commande s’ouvre, tapez la commande indiquée à l’étape 2, ci-dessus. 
  
Le mode Négocier est utilisé à chaque fois que le nœud observateur ne peut pas être configuré en tant que pool d’application approuvées. Dans ce mode, les administrateurs devront gérer les mots de passe des utilisateurs de test sur le nœud observateur.
  

