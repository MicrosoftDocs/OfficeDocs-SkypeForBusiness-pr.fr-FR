---
title: Installation et configuration des nœuds observateurs
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 'Résumé : Installez et configurez les nœuds observateurs pour Skype pour les transactions synthétiques Business Server.'
ms.openlocfilehash: 6719826515954290f30eac272f638b846f45142a
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "25375985"
---
# <a name="install-and-configure-watcher-nodes"></a>Installation et configuration des nœuds observateurs
 
**Résumé :** Installez et configurez les nœuds observateurs pour Skype pour les transactions synthétiques Business Server.
  
Nœuds observateurs sont des ordinateurs qui exécutent régulièrement Skype pour les transactions synthétiques Business Server. Les transactions synthétiques sont des applets de commande Windows PowerShell qui vérifient que les scénarios utilisateur clés, comme la capacité à se connecter ou à échanger des messages instantanés, fonctionnent comme prévu. Pour Skype pour Business Server 2015, System Center Operations Manager peuvent exécuter les transactions synthétiques indiquées dans le tableau suivant, qui inclut les trois types de transaction synthétique :
  
- **Par défaut** Transactions synthétiques un nœud Observateur s’exécute par défaut. Lorsque vous créez un nœud observateur, vous pouvez spécifier les transactions synthétiques exécutées par ce nœud. (C’est le rôle du paramètre Tests utilisé par l’applet de commande New-CsWatcherNodeConfiguration.) Si vous n’utilisez pas le paramètre Tests lorsque le nœud observateur est créé, il s’exécute automatiquement toutes les transactions synthétiques par défaut et exécutera pas les transactions synthétiques Non par défaut. Cela signifie, par exemple, que le nœud observateur est configuré de manière à exécuter le test Test-CsAddressBookService, mais qu’il ne l’est pas pour exécuter le test Test-CsExumConnectivity.
    
- **Par défaut** Tests de nœuds observateurs n’exécutent pas par défaut. (Pour plus d’informations, voir la description du type par défaut). Toutefois, le nœud observateur peut être activé pour exécuter des transactions synthétiques Non par défaut. Vous pouvez le faire lorsque vous créez le nœud observateur (à l’aide de l’applet de commande New-CsWatcherNodeConfiguration), ou n’importe quel moment après le nœud observateur a été créé. Notez que la plupart des transactions synthétiques Non par défaut nécessitent des étapes de configuration supplémentaires. Pour plus d’informations sur ces étapes, voir Instructions d’installation spéciales pour les Transactions synthétiques. Pour plus d’informations sur ces étapes, voir [Instructions d’installation spéciales pour les Transactions synthétiques ](test-users-and-settings.md#special_synthetictrans).
    
- **Étendue** Un type particulier de transaction synthétique Non par défaut. Contrairement à d’autres transactions synthétiques, les tests étendus peuvent être exécutés plusieurs fois à chaque passage. Cela peut s’avérer utile pour vérifier des comportements tels que plusieurs itinéraires des communications vocales sur le réseau téléphonique commuté (RTC) pour un pool. Vous pouvez configurer cette fonction en ajoutant simplement plusieurs instances d’un test étendu à un nœud observateur.
    
Pour plus d’informations sur la procédure d’ajout d’autres transactions synthétiques à un nœud observateur, reportez-vous à la rubrique [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans) (contenu éventuellement en anglais). Vous pouvez également utiliser Skype pour Business Server Management Shell pour supprimer les transactions synthétiques d’un nœud Observateur.
  
Les transactions synthétiques accessibles aux nœuds observateur sont, par exemple :
  
|**Nom de l’applet de commande (nom du test)**|**Description**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Confirme que les utilisateurs peuvent rechercher des utilisateurs qui ne figurent pas dans leur liste des contacts.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Confirme que les utilisateurs peuvent rechercher des utilisateurs qui ne figurent pas dans leur liste de contacts via HTTP.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Confirme que les utilisateurs peuvent créer des conférences audio/vidéo et y participer.  <br/> |
|Test-CsGroupIM (conférences de messagerie instantanée)  <br/> |Confirme que les utilisateurs peuvent envoyer des messages instantanés dans des conférences et participer à des conversations par messagerie instantanée comptant trois personnes ou plus.  <br/> |
|Test-CsIM (messagerie instantanée P2P)  <br/> |Confirme que les utilisateurs peuvent envoyer des messages instantanés P2P.  <br/> |
|Test-CsP2PAV (AV P2P)  <br/> |Confirme que les utilisateurs peuvent passer des appels audio P2P (signalisation uniquement).  <br/> |
|Test-CsPresence (Présence)  <br/> |Confirme que les utilisateurs sont en mesure d’afficher la présence d’autres utilisateurs.  <br/> |
|Test-CsRegistration (Enregistrement)  <br/> |Confirme que les utilisateurs peuvent se connecter à Skype pour les entreprises.  <br/> |
|Test-CsPstnPeerToPeerCall (RTC)  <br/> |Confirme que les utilisateurs peuvent passer des appels à des personnes à l’extérieur de l’entreprise et recevoir des appels de celles-ci (numéros RTC).  <br/> |
|Test-CsASConference (ASConference)  <br/> |Confirme que les utilisateurs peuvent créer des conférences de partage d’applications et y participer.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Confirme que les serveurs Edge audio/vidéo peuvent accepter des connexions pour les appels et les téléconférences P2P.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Confirme que les utilisateurs peuvent participer à une conférence de collaboration de données (une réunion en ligne qui comprend des activités, comme des tableaux blancs et des sondages).  <br/> |
|Test-CsDialInConferencing (DialInConferencing)  <br/> |Confirme que les utilisateurs peuvent composer des numéros pour participer à des conférences.  <br/> |
|Test-Cs DialInConferencing (DialInConferencing)  <br/> |Confirme que les utilisateurs peuvent composer des numéros pour participer à des conférences.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Confirme qu’un utilisateur peut se connecter à Exchange messagerie unifiée (MU).  <br/> |
|Test-CsGroupIM - TestJoinLauncher (JoinLauncher)  <br/> |Confirme que les utilisateurs peuvent créer des réunions planifiées et y participer (en cliquant sur un lien d’adresse web).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Confirme que les utilisateurs d’appareil mobile peuvent s’enregistrer et envoyer des messages instantanés.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Confirme que le serveur interopérabilité vidéo fonctionne et peut gérer les connexions entrantes sur une jonction SIP vidéo.  <br/> **Remarque :** Prise en charge MCX pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Confirme que les utilisateurs peuvent échanger des messages à l’aide du service de conversation permanente.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Confirme que les utilisateurs peuvent participer à des conférences par le biais du web.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Confirme que les contacts d’un utilisateur sont accessibles par le biais du magasin de contacts unifié. Le magasin de contacts unifié permet aux utilisateurs de conserver un ensemble unique de contacts qui est accessible à l’aide de Skype pour Business Server 2015, la messagerie Outlook et client de collaboration, et/ou d’Outlook Web Access.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Confirme qu’un message instantané peut être envoyé par le biais de la passerelle Extensible Messaging and Presence Protocol (XMPP).  <br/> XMPP passerelles et les proxys sont disponibles dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019.  |

Il est inutile d’installer les nœuds observateurs afin d’utiliser System Center Operations Manager. Si vous n’installez pas ces nœuds, vous pouvez toujours obtenir des alertes en temps réel à partir de Skype pour les composants Business Server 2015 chaque fois qu’un problème se produit. (Les utilisateurs Management Pack n’utilise pas nœuds observateurs.) Toutefois, les nœuds observateurs sont requis si vous souhaitez surveiller les scénarios de bout en bout à l’aide du pack d’administration d’analyse Active.
  
> [!NOTE]
> De même, les administrateurs peuvent exécuter manuellement des transactions synthétiques sans utiliser ou installer Operations Manager. Selon la taille de votre Skype pour le déploiement de serveur d’entreprise, les transactions synthétiques peuvent utiliser une grande quantité de temps mémoire et du processeur d’ordinateur. Pour cette raison, nous vous recommandons d’utiliser un ordinateur dédié comme nœud observateur. Par exemple, vous ne devez pas configurer un Skype pour Business Server serveur frontal pour agir comme un nœud Observateur. Nœuds observateurs doivent satisfaire les exigences de matériel de base même comme tout autre ordinateur dans votre Skype pour la topologie du serveur d’entreprise. 
  
> [!NOTE]
> Un nœud Observateur de Lync Server 2013 hérité ne peut pas se trouver sur le même ordinateur en tant qu’un Skype pour le nœud Observateur de Business Server 2015, car les fichiers du système principal pour Lync Server 2013 et Skype pour Business Server 2015 ne peut pas être installés sur le même ordinateur. Toutefois, Skype pour les nœuds Observateur Business Server 2015 peut surveiller simultanément Skype pour Business Server 2015 et Lync Server 2013. Transactions synthétiques par défaut sont prises en charge pour les versions de produit. 
  
Nœuds Observateur de Lync Server 2013 peuvent être déployés à l’intérieur ou à l’extérieur d’une entreprise afin de vérifier :
  
- Connectivité avec les pools pour les utilisateurs situés dans l’entreprise
    
- Connectivité par le biais des réseaux de périmètre pour les utilisateurs distants travaillant à l’extérieur de l’entreprise
    
- Connectivité avec les Branch Office Appliances
    
- Connectivité à Lync Server 2013 au sein de l’entreprise et par le biais des réseaux de périmètre.
    
Différentes options d’authentification sont disponibles pour l’intérieur et l’extérieur de l’entreprise afin de simplifier l’administration. Pour plus d’informations, reportez-vous à la rubrique [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).
  
Pour configurer un ordinateur comme nœud observateur, vous devez d’abord remplir les conditions préalables suivantes : 
  
- Installation de System Center Operations Manager et importez le Skype pour les packs d’administration Business Server 2015. Vous devez également tout d’abord vérifier que l’ordinateur nœud Observateur remplit toutes les conditions préalables pour l’installation de Skype pour Business Server 2015.
    
- Installez les composants ci-dessous sur l’ordinateur du nœud observateur :
    
  - La version complète du .NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Une fois que les conditions préalables sont respectées, vous pouvez configurer le nœud observateur en procédant comme suit :
  
1. Installez le Skype pour Business Server 2015 principaux fichiers sur l’ordinateur de nœud Observateur.
    
2. Installez l’agent System Center Operations Manager sur l’ordinateur de nœud Observateur.
    
3. Exécutez le fichier exécutable Watchernode.msi.
    
4. Utilisez les applets de commande **New-CsWatcherNodeConfiguration** pour configurer les utilisateurs de test employés par le nœud observateur
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Installez les fichiers principaux de Skype Entreprise Server 2015 et la base de données RTCLocal.

Pour installer le Skype pour Business Server 2015 principaux fichiers sur un ordinateur, procédez comme suit. La base de données RTCLocal est installée automatiquement lorsque vous installez les fichiers principaux. Notez que vous n’avez pas besoin installer SQL Server sur les nœuds Observateur. SQL Server Express sont automatiquement installées.
  
Pour installer le Skype pour Business Server 2015 principaux fichiers et la base de données RTCLocal :
  
1. Sur l’ordinateur nœud observateur, sélectionnez Démarrer, Tous les programmes, Accessoires, cliquez avec le bouton droit sur Invite de commandes, puis cliquez sur Exécuter en tant qu’administrateur.
    
2. Dans la fenêtre de console, tapez la commande ci-dessous, puis appuyez sur Entrée. Veillez à entrer le chemin d’accès approprié pour votre Skype pour les fichiers d’installation Business Server : D:\Setup.exe /BootstrapLocalMgmtTo vérifier que le principaux Skype pour les composants Business Server sont installés avec succès, cliquez sur **Démarrer**, sur **Tous les programmes**, Cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour Business Server Management Shell**. Dans Skype pour Business Server Management Shell, tapez la commande Windows PowerShell suivante et appuyez sur ENTRÉE :
  
```
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> La première fois que vous exécutez cette commande, elle ne renvoie aucune donnée, car vous n’avez pas encore configuré de nœud observateur. Si la commande est exécutée sans le renvoi d’une erreur, vous pouvez supposer que le Skype pour le programme d’installation de Business Server s’est correctement effectuée. 
  
Si votre nœud observateur se trouve à l’intérieur de votre réseau de périmètre, exécutez la commande ci-dessous pour vérifier l’installation de Skype Entreprise Server 2015 :
  
Get-CsPinPolicyYou recevra des informations semblables aux suivantes, selon le nombre de stratégies de code confidentiel configurées pour être utilisées dans votre organisation :
  
Identité : globale
  
Description :
  
MinPasswordLength : 5
  
PINHistoryCount : 0
  
AllowCommonPatterns : False
  
PINLifetime : 0
  
MaximumLogonAttempts :
  
Si des informations sur vos stratégies de code confidentiel s’affichent, les composants principaux ont été installés correctement.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Installation des fichiers d’agent Operation Manager sur un nœud observateur

Similaire aux Skype pour le programme d’installation de Business Server pour les rapports d’alertes de composants, un Skype pour le nœud Observateur de Business Server 2015 nécessite installation des fichiers agent System Center Operations Manager. Ainsi, les transactions synthétiques à exécuter et les alertes à signaler pour le serveur de gestion de System Center Operations Manager racine.
  
Pour installer les fichiers d’agent, suivez les procédures répertoriées dans [configurer le Skype pour les ordinateurs Business Server qui seront surveillés](configure-computers-to-monitor.md).
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Configuration d’un nœud observateur pour exécuter des transactions synthétiques
<a name="enable_synthetic_trans"> </a>

Après avoir installé les fichiers de l’agent System Center Operations Manager, vous devez configurer le nœud Observateur proprement dit. La procédure varie selon que l’ordinateur du nœud observateur se trouve à l’intérieur ou à l’extérieur de votre réseau de périmètre. 
  
Lorsque vous configurez un nœud observateur, vous devez également sélectionner le type de méthode d’authentification utilisé par ce nœud. Skype pour Business Server 2015 vous permet de choisir une des deux méthodes d’authentification : serveur approuvé ou l’authentification des informations d’identification. Les différences entre ces deux méthodes sont indiquées dans le tableau suivant :
  
||**Description**|**Emplacements pris en charge**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Utilise un certificat pour emprunter l’identité d’un serveur interne et contourner les demandes d’authentification.  <br/> Utile pour les administrateurs qui préfèrent gérer un seul certificat au lieu de plusieurs mots de passe d’utilisateur sur chaque nœud observateur.  <br/> |Dans l’entreprise  <br/> Avec cette méthode, le nœud observateur doit se trouver dans le même domaine que les pools surveillés. Si le nœud observateur et les pools se trouvent dans des domaines différents, utilisez l’authentification des informations d’identification à la place.  <br/> |
|Negotiate  <br/> |Stocke les noms d’utilisateur et les mots de passe de manière sécurisée dans le Gestionnaire d’informations d’identification Windows sur chaque nœud observateur.  <br/> Ce mode implique davantage d’opérations de gestion des mots de passe, mais c’est la seule option pour les nœuds observateurs situés en dehors de l’entreprise. Ces nœuds observateurs ne peuvent pas être traités comme un point de terminaison approuvé pour l’authentification.  <br/> |En dehors de l’entreprise  <br/> Dans l’entreprise  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Configure un nœud observateur pour l’utilisation de l’authentification des serveurs approuvés.
<a name="enable_synthetic_trans"> </a>

Si votre ordinateur de nœud observateur se trouve dans le réseau de périmètre, l’utilisation de l’authentification de type Serveur sécurisé permet de réduire considérablement les tâches d’administration en gérant un certificat unique à la place des nombreux mots de passe de comptes d’utilisateurs.
  
Pour configurer l’authentification de type Serveur sécurisé, vous devez d’abord créer un pool d’applications approuvées afin d’héberger l’ordinateur du nœud observateur. Une fois que vous avez créé le pool d’applications approuvées, vous devez configurer puis les transactions synthétiques sur ce nœud observateur pour exécuter en tant que les applications approuvées.
  
> [!NOTE]
> Une application approuvée est une application qui reçoit l’état approuvé à exécuter dans le cadre de Skype pour Business Server 2015, mais n’est pas un composant intégré du produit. Le statut approuvé signifie que l’application n’a pas à s’authentifier chaque fois qu’elle est exécutée.
  
Pour créer un pool d’applications approuvées, ouvrez le Skype pour Business Server Management Shell et exécutez une commande similaire à celle-ci :
  
```
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Pour plus d’informations sur les paramètres dans la commande précédente, tapez ce qui suit à partir de la Skype pour invite Business Server Management Shell : 
  
```
Get-Help New-CsTrustedApplicationPool -Full | more
```

Après avoir créé le pool d’applications approuvées, configurez l’ordinateur du nœud observateur afin qu’il exécute les transactions synthétiques sous forme d’applications approuvées. À cet effet, utilisez l’applet de commande **New-CsTrustedApplication** et une commande comme celle-ci :
  
```
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Une fois que l’exécution de cette commande est terminée et que l’application approuvée a été créée, exécutez l’applet de commande **Enable-CsTopology** pour vous assurer que les modifications sont appliquées :
  
```
Enable-CsTopology
```

Après l’exécution de l’applet de commande Enable-Cs Topology, redémarrez l’ordinateur.
  
Pour vérifier que la nouvelle application approuvée a été créée, tapez ce qui suit à le Skype pour invite Business Server Management Shell :
  
```
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Configuration d’un certificat par défaut sur le nœud observateur
<a name="enable_synthetic_trans"> </a>

Chaque nœud observateur qui utilise l’authentification TrustedServer doit avoir un certificat par défaut affecté à l’aide de la Skype pour l’Assistant de déploiement de serveur d’entreprise. 
  
Pour affecter un certificat par défaut :
  
1. Cliquez sur Démarrer, sur tous les programmes, cliquez sur Skype pour Business Server 2015, puis cliquez sur Skype pour l’Assistant de déploiement Business Server. 
    
2. Dans Skype pour l’Assistant de déploiement Business Server, cliquez sur Installer ou mettre à jour Skype pour le système de serveur d’entreprise, puis cliquez sur exécuter sous l’en-tête de la demande, installer ou assigner les certificats. 
    
> [!NOTE]
> Si le bouton Exécuter est désactivé, vous devrez peut-être d’abord cliquer sur Exécuter sous Installer le magasin de configurations local. 
  
Effectuez l’une des actions suivantes :
  
- Si vous possédez déjà un certificat qui peut être utilisé comme certificat par défaut, cliquez sur Par défaut dans l’Assistant Certificat, puis cliquez sur Attribuer. Suivez les étapes de l’Assistant permettant d’affecter un certificat pour affecter ce certificat.
    
- Si vous devez demander un certificat à utiliser comme certificat par défaut, cliquez sur Demander, puis suivez les étapes de l’Assistant Demande de certificat pour demander ce certificat. Si vous utilisez les valeurs par défaut pour le certificat de serveur web, vous obtenez un certificat que vous pouvez affecter comme certificat par défaut.
    
## <a name="install-and-configure-a-watcher-node"></a>Installation et configuration d’un nœud observateur
<a name="enable_synthetic_trans"> </a>

Après avoir redémarré l’ordinateur de nœud observateur et configuré un certificat, vous devez exécuter le fichier Watchernode.msi. (Vous devez exécuter Watchernode.msi sur n’importe quel ordinateur où sont installés les fichiers de l’agent Operations Manager et le Skype pour les composants principaux de Business Server 2015.) 
  
Pour installer et configurer un nœud observateur :
  
1. Ouvrez le Skype pour Business Server Management Shell en cliquant sur Démarrer, sur tous les programmes, cliquez sur Skype pour Business Server 2015, puis en cliquant sur Skype pour Business Server Management Shell. 
    
2. Dans Management Shell, tapez la commande ci-dessous, puis appuyez sur Entrée (spécifiez le chemin d’accès réel de votre copie de Watchernode.msi) :
    
```
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> Vous pouvez également exécuter Watchernode.msi à partir d’une fenêtre de commande. Pour ouvrir une fenêtre de commande, cliquez sur Démarrer, cliquez avec le bouton droit sur Invite de commandes, puis cliquez sur Exécuter en tant qu’administrateur. Lorsque la fenêtre de commande s’affiche, tapez la commande indiquée lors de l’étape 2 ci-dessus. 
  
> [!IMPORTANT]
> Dans la commande précédente, la paire nom/valeur Authentication=TrustedServer dépend des minuscules et des majuscules. Vous devez la saisir exactement comme indiqué. Par exemple, si vous ne respectez pas l’emploi des minuscules et des majuscules, cette commande échouera : 
  
```
C:\Tools\Watchernode.msi authentication=trustedserver
```

Vous pouvez utiliser le mode TrustedServer uniquement avec les ordinateurs situés dans le réseau de périmètre. Lorsqu’un nœud observateur est exécuté en mode TrustedServer, les administrateurs n’ont pas à gérer les mots de passe des utilisateurs de test sur l’ordinateur.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Configuration d’un nœud observateur de manière à utiliser la négociation
<a name="enable_synthetic_trans"> </a>

Si votre ordinateur de nœud observateur se trouve en dehors du réseau de périmètre, vous devez suivre une procédure légèrement différente pour configurer ce nœud observateur de sorte qu’il exécute des transactions synthétiques : en particulier, vous ne devez pas créer de pool d’applications approuvées ou d’application approuvée. Cela signifie que vous devrez effectuer les deux tâches suivantes.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Mise à jour de l’appartenance au groupe « RTC Local Read-Only Administrators »

Si votre ordinateur de nœud observateur se trouve en dehors du réseau de périmètre, vous devez ajouter le compte Service réseau au groupe « RTC Local Read-only Administrators » sur l’ordinateur de nœud observateur. Pour cela, procédez comme suit sur le nœud observateur :
  
1. Cliquez sur Démarrer, cliquez avec le bouton droit sur Ordinateur, puis sur Gérer.
    
2. Dans le Gestionnaire de serveur, développez Configuration et Utilisateurs et groupes locaux, puis cliquez sur Groupes.
    
3. Dans le volet Groupes, double-cliquez sur RTC Local Read-only Administrators.
    
4. Dans la boîte de dialogue RTC Local Read-only Administrators - Propriétés, cliquez sur Ajouter.
    
5. Dans la boîte de dialogue Sélectionner des utilisateurs, des ordinateurs, des comptes de service ou des groupes, cliquez sur Emplacements.
    
6. Dans la boîte de dialogue Emplacements, sélectionnez le nom de l’ordinateur de nœud observateur, puis cliquez sur OK.
    
7. Dans la zone Entrer les noms d’objets à sélectionner, tapez Service réseau, puis cliquez sur OK.
    
8. Dans la boîte de dialogue RTC Local Read-only Administrators - Propriétés, cliquez sur OK, puis fermez le Gestionnaire de serveur.
    
9. Redémarrez l’ordinateur de nœud observateur.
    
### <a name="install-the-watcher-node-configuration-files"></a>Installation des fichiers de configuration du nœud observateur

L’étape suivante consiste à exécuter le fichier Watchernode.msi : 
  
1. Ouvrez Microsoft Skype Entreprise Server 2015 Management Shell. Sélectionnez Démarrer, Tous les programmes, Microsoft Skype Entreprise Server 2015, puis cliquez sur Skype Entreprise Server Management Shell. 
    
2. Dans Skype Entreprise Server Management Shell, tapez la commande ci-dessous, puis appuyez sur Entrée (veillez à spécifier le chemin d’accès réel de votre copie de Watchernode.msi) :
    
   ```
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Comme indiqué précédemment, vous pouvez également exécuter Watchernode.msi à partir d’une fenêtre de commande. Pour ouvrir une fenêtre de commande, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**. Lorsque la fenêtre de commande s’affiche, tapez la commande utilisée lors de l’étape 2 ci-dessus. 
  
Le mode Négocier est utilisé chaque fois que le nœud observateur ne peut pas être configuré comme pool d’application approuvées. Dans ce mode, les administrateurs devront gérer les mots de passe des utilisateurs de test sur le nœud observateur.
  

