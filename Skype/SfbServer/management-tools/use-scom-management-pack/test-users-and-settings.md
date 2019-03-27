---
title: Configuration des paramètres et des utilisateurs test de nœud observateur
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 'Résumé : Configurez des comptes d’utilisateurs de test et les paramètres du nœud observateur pour Skype pour les transactions synthétiques Business Server.'
ms.openlocfilehash: 121e07d8bee20bef1b8fd4b06e51cf0313c018d0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895215"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Configuration des paramètres et des utilisateurs test de nœud observateur
 
**Résumé :** Configurer les comptes d’utilisateurs de test et les paramètres du nœud observateur pour Skype pour les transactions synthétiques Business Server.
  
Après avoir configuré l’ordinateur qui jouera le rôle de nœud observateur, vous devez :
  
1. [Configurer les comptes d’utilisateurs Test](test-users-and-settings.md#testuser) devant être utilisé par les nœuds Observateur. Si vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser l’applet de commande **Set-CsTestUserCredential** pour activer ces comptes pour une utilisation sur le nœud observateur.
    
2. Mettre à jour les paramètres de configuration du nœud observateur.
    
## <a name="configure-test-user-accounts"></a>Configurer les comptes d’utilisateurs tests
<a name="testuser"> </a>

Comptes de test n’avez pas besoin représenter les personnes réelle, mais ils doivent être des comptes Active Directory valides. En outre, ces comptes doivent être activés pour Skype pour Business Server, ils doivent avoir des adresses SIP valides, et ils doivent être activés pour Enterprise Voice (utiliser la transaction synthétique Test-CsPstnPeerToPeerCall). 
  
Si vous utilisez la méthode d’authentification TrustedServer, il vous suffit de vous assurer que ces comptes existent et configurez-les comme indiqué. Vous devez affecter au moins deux utilisateurs test pour chaque pool que vous souhaitez tester. Si vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser l’applet de commande Set-cstestusercredential n’et le Skype pour Business Server Management Shell activer ces comptes pour travailler avec les transactions synthétiques de test. Cela en exécutant une commande semblable à ce qui suit (les commandes suivantes partent du principe que les deux comptes d’utilisateur Active Directory ont été créés et que ces comptes sont activés pour Skype pour Business Server) :
  
```
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

Vous devez inclure non seulement l’adresse SIP, mais également le nom d’utilisateur et le mot de passe. Si vous omettez le mot de passe, l’applet de commande Set-CsTestUserCredential vous invitera à entrer ces informations. Le nom d’utilisateur peut être spécifié au format nom de domaine/nom d’utilisateur indiqué ci-dessus dans le bloc de code précédent.
  
Pour vérifier que les informations d’identification utilisateur de test ont été créées, exécutez ces commandes à partir de la Skype pour Business Server Management Shell :
  
```
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

Des informations semblables aux suivantes sont retournées pour chaque utilisateur :
  
|**nom d'utilisateur**|**mot de passe**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurer un nœud observateur de base avec les transactions synthétiques par défaut

Une fois les utilisateurs tests créés, vous pouvez créer un nœud observateur en exécutant une commande semblable à la suivante :
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

Cette commande crée un nœud observateur qui utilise les paramètres par défaut et exécute le jeu de transactions synthétiques par défaut. Le nouveau nœud Observateur utilise également le test utilisateurs watcher1@litwareinc.com et watcher2@litwareinc.com. Si le nœud Observateur utilise l’authentification TrustedServer, les comptes de deux test peuvent être des comptes d’utilisateur valide pour Active Directory et Skype pour Business Server. Si le nœud observateur utilise la méthode d’authentification Negotiate, vous devez également activer ces comptes d’utilisateurs pour le nœud observateur à l’aide de l’applet de commande Set-CsTestUserCredential.
  
Pour vérifier que la découverte automatique du pool cible pour se connecter est correctement configurée, au lieu de cibler un pool directement, utilisez les étapes suivantes :
  
```
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Configuration de tests étendus

Si vous souhaitez activer le test PSTN, qui vérifie la connectivité avec le réseau téléphonique commuté, vous devez effectuer certaines tâches de configuration supplémentaires lors de la configuration du nœud observateur. Tout d’abord, vous devez associer vos utilisateurs test au type de test PSTN en exécutant une commande semblable à la suivante à partir de Skype Entreprise Server Management Shell :
  
```
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Les résultats de cette commande doivent être stockés dans une variable. Dans cet exemple, il s’agit de la variable nommée $pstnTest. 
  
Ensuite, vous pouvez utiliser l’applet de commande **New-CsWatcherNodeConfiguration** pour associer le type de test (stocké dans la variable $pstnTest) à un Skype pour le pool de serveurs d’entreprise. Par exemple, la commande suivante crée une nouvelle configuration de nœud observateur pour le pool atl-cs-001, ajout de deux utilisateurs test créés précédemment, et ajout de la passerelle PSTN type de test :
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

La commande précédente échoue si vous n’avez pas installé les fichiers principaux de Skype Entreprise Server et la base de données RTCLocal sur l’ordinateur nœud observateur. 
  
Pour tester plusieurs stratégies de voix, vous pouvez créer un test étendu pour chaque stratégie à l’aide de l’applet de commande **New-Cs ExtendedTest**. Les utilisateurs fournis doivent être configurés avec les stratégies de voix souhaitées. Les tests étendus sont ensuite passés à l’applet de commande **New-CsWatcherNodeConfiguration** à l’aide de virgules de délimitation, comme suit :
  
-ExtendedTests @{ajouter = $pstnTest1, $pstnTest2, $pstnTest3}
  
Dans la mesure où l’applet de commande **New-CsWatcherNodeConfiguration** est appelée sans utiliser le paramètre Tests, seules les transactions synthétiques par défaut (et la transaction synthétique étendue spécifiée) seront activées pour le nouveau nœud observateur. Dans ce cas, le nœud observateur testera les composants suivants :
  
- Enregistrement
    
- IM
    
- GroupIM (messagerie instantanée de groupe)
    
- P2PAV (sessions audio/vidéo d’égal à égal)
    
- AvConference (audioconférence)
    
- Presence
    
- ABS (Service de carnet d’adresses)
    
- ABWQ (Service web de carnet d’adresses)
    
Les composants suivants ne seront pas testés par défaut :
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialInConferencing
    
- ExumConnectivity (Messagerie unifiée Exchange)
    
- JoinLauncher
    
- MCXP2PIM (messagerie instantanée hérité appareil mobile)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (appels de passerelle PSTN, spécifiés comme test étendu.)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>Ajout et suppression de transactions synthétiques

Après avoir configuré un nœud observateur, vous pouvez utiliser l’applet de commande Set-CsWatcherNodeConfiguration pour ajouter ou supprimer des transactions synthétiques du nœud. Par exemple, pour ajouter le test PersistentChatMessage au nœud observateur, utilisez la méthode Add et une commande semblable à la suivante :
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

Plusieurs tests peuvent être ajoutés en séparant leur nom par des virgules. Par exemple :
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

Une erreur se produit si un ou plusieurs de ces tests (par exemple DataConference) ont déjà été activés sur le nœud observateur. Dans ce cas, vous recevez un message d’erreur semblable au suivant :
  
Set-CsWatcherNodeConfiguration : il existe une combinaison de clés dupliquée « DataConference » pour la clé « urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName » ou une contrainte d’identité unique.
  
Lorsque cette erreur se produit, aucune modification n’est appliquée. La commande doit être réexécutée en supprimant le test dupliqué.
  
Pour supprimer une transaction synthétique d’un nœud observateur, utilisez la méthode Remove. Par exemple, la commande suivante supprime le test ABWQ d’un nœud observateur :
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Vous pouvez utiliser la méthode Replace pour remplacer tous les tests activés actuellement par un ou plusieurs nouveaux tests. Par exemple, si vous souhaitez que le nœud observateur exécute seulement le test de messagerie instantanée, vous pouvez exécuter la commande suivante :
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Lorsque vous exécutez cette commande, toutes les transactions synthétiques sur le nœud observateur spécifié sont désactivées, à l’exception de la messagerie instantanée.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Affichage et test de la configuration du nœud observateur

Si vous souhaitez afficher les tests qui ont été assignés à un nœud observateur, exécutez une commande semblable à la suivante :
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Cette commande retourne des informations semblables aux suivantes, en fonction des transactions synthétiques qui ont été assignées au nœud :
  
Inscription par messagerie instantanée GroupIM P2PAV AvConference présence PersistentChatMessage DataConference
> [!TIP]
> Pour afficher les transactions synthétiques par ordre alphabétique, exécutez plutôt la commande suivante : 
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Pour vérifier qu’un nœud observateur a été créé, tapez la commande suivante à partir de Skype Entreprise Server Management Shell :
  
```
Get-CsWatcherNodeConfiguration
```

Des informations semblables aux suivantes sont retournées :
  
Identité : atl-cs-001 <br/>
TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}<br/>
ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}<br/>
TargetFqdn : atl-cs-001<br/>
Numéro_port : 5061<br/>

Pour vérifier que le nœud observateur a été correctement configuré, tapez la commande suivante à partir de Skype Entreprise Server Management Shell :
  
```
Test-CsWatcherNodeConfiguration
```

Cette commande teste chaque nœud observateur de votre déploiement et vérifie si :
  
- Le rôle de serveur d’inscriptions requis est installé.
    
- La clé de Registre obligatoire est créée (terminée lorsque vous avez exécuté l’applet de commande Set-CsWatcherNodeConfiguration).
    
- Vos serveurs exécutent la version correcte de Skype pour Business Server.
    
- Si vos ports sont correctement configurés.
    
- Vos utilisateurs de test assignés disposent les informations d’identification requises.
    
## <a name="managing-watcher-nodes"></a>Gestion des nœuds observateurs
<a name="testuser"> </a>

En plus de modifier les transactions synthétiques qui sont exécutées sur un nœud observateur, vous pouvez également utiliser l’applet de commande **Set-CsWatcherNodeConfiguration** pour effectuer deux autres tâches importantes : d’une part, l’activation et la désactivation du nœud observateur et, d’autre part, la configuration du nœud observateur pour utiliser des URLweb internes ou externes lors de l’exécution de ses tests.
  
Par défaut, les nœuds observateurs sont conçus pour exécuter régulièrement toutes leurs transactions synthétiques activées. Parfois, cependant, vous souhaiterez peut-être suspendre ces transactions. Par exemple, si le nœud observateur est temporairement déconnecté du réseau, il est inutile d’exécuter les transactions synthétiques. Sans connectivité réseau, ces transactions sont vouées à l’échec. Pour désactiver temporairement un nœud observateur, exécutez une commande semblable à celle-ci à partir de Skype Entreprise Server Management Shell :
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Cette commande désactive l’exécution des transactions synthétiques sur le nœud observateur atl 001.litwareinc.com. Pour reprendre l’exécution des transactions synthétiques, affectez à la propriété Enabled la valeur True ($True) :
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> La propriété Enabled peut être utilisée pour activer ou désactiver les nœuds observateurs. Si vous souhaitez supprimer définitivement un nœud observateur, utilisez l’applet de commande **Remove-CsWatcherNodeConfiguration** :
  
```
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Cette commande supprime tous les paramètres de configuration du nœud observateur de l’ordinateur spécifié, ce qui empêche ainsi l’ordinateur d’exécuter automatiquement des transactions synthétiques. Toutefois, la commande ne désinstalle pas les fichiers de l’agent System Center ou la Skype pour les fichiers système Business Server.
  
Par défaut, les nœuds observateurs utilisent les URL web externes d’une organisation dans le cadre de leurs tests. Cependant, les nœuds observateurs peuvent également être configurés de manière à utiliser les URL web internes de l’organisation. Cela permet aux administrateurs de vérifier l’accès URL pour les utilisateurs situés à l’intérieur du réseau de périmètre. Pour configurer un nœud observateur de manière à utiliser des URL internes à la place d’URL externes, affectez à la propriété UseInternalWebURls la valeur True ($True) :
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

La réinitialisation de cette propriété à la valeur par défaut False ($False) fera que l’observateur utilisera de nouveau les URL externes :
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Instructions d’installation spéciales pour les transactions synthétiques
<a name="special_synthetictrans"> </a>

La plupart des transactions synthétiques peuvent s’exécuter sur un nœud observateur en l’état. Dans la plupart des cas, dès que la transaction synthétique est ajoutée aux paramètres de configuration du nœud observateur, ce dernier peut commencer à utiliser la transaction synthétique lors de ses tests. Toutefois, il existe des transactions synthétiques qui nécessitent des instructions d’installation spéciales, comme détaillé dans les sections suivantes.
  
### <a name="data-conferencing-synthetic-transaction"></a>Transaction synthétique de conférence de données

Si votre ordinateur de nœud observateur se situe à l’extérieur de votre réseau de périmètre, vous ne pourrez probablement pas exécuter la transaction synthétique de conférence de données à moins que vous ne désactiviez au préalable les paramètres proxy du navigateur Internet Windows Internet Explorer® pour le compte Service réseau, en procédant de la manière suivante :
  
1. Sur l’ordinateur nœud observateur, cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.
    
2. Dans la fenêtre de console, tapez la commande suivante, puis appuyez sur Entrée : 
    
```
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

Le message suivant s’affiche dans la fenêtre Commande :
  
BITSAdmin est déconseillé et ne sera peut-être pas disponible dans les versions ultérieures de Windows. Les outils d’administration pour le service BITS sont désormais fournis par les applets de commande BITS PowerShell.
  
Les paramètres proxy Internet pour le compte NetworkService sont définis sur NO_PROXY. 
  
(connection = default)
  
Ce message signifie que vous avez désactivé les paramètres proxy d’Internet Explorer pour le compte Service réseau.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Transaction synthétique de la messagerie unifiée Exchange

La transaction synthétique de la messagerie unifiée Exchange vérifie que les utilisateurs test peuvent se connecter à des comptes de messagerie vocale hébergés dans Exchange.
  
Les utilisateurs test doivent être préconfigurés avec des comptes de messagerie vocale. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Transaction synthétique de conversation permanente

Pour utiliser la transaction synthétique de conversation permanente, vous devez d’abord créer un canal et donner aux utilisateurs test l’autorisation de l’utiliser.
  
Vous pouvez utiliser la transaction synthétique de conversation permanente pour configurer ce canal : 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Vous devez exécuter cette tâche de configuration au sein de l’entreprise :
  
- Si elle est exécutée à partir d’un ordinateur non-serveur, l’utilisateur qui exécute l’applet de commande doit être membre du rôle CsPersistentChatAdministrators pour le contrôle d’accès en fonction du rôle (RBAC).
    
- Si elle est exécutée à partir du serveur lui-même, l’utilisateur qui exécute l’applet de commande doit être membre du groupe RTCUniversalServerAdmins.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Transaction synthétique pour les appels d’égal à égal PSTN

La transaction synthétique Test-CSPstnPeerToPeerCall vérifie la capacité de passer et recevoir des appels via le réseau téléphonique commuté (PSTN).
  
Pour exécuter cette transaction synthétique, vous devez configurer les éléments suivants :
  
- Deux utilisateurs test (un appelant et un récepteur) activés pour les communications unifiées (UC).
    
- Numéros de sélection directe à l’arrivée (SDA) pour chaque compte d’utilisateur.
    
- Itinéraires voix et stratégies VoIP qui autorisent les appels au numéro du récepteur d’atteindre la passerelle PSTN.
    
- Une passerelle PSTN qui accepte l’appel et les médias qui achemine les appels vers le pool d’accueil d’un récepteur, en fonction du numéro composé.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Transaction synthétique du magasin de contacts unifié

La transaction synthétique du magasin de contacts unifié vérifie la capacité de Skype pour Business Server récupérer des contacts au nom d’un utilisateur à partir d’Exchange.
  
Pour utiliser cette transaction synthétique, les conditions suivantes doivent être remplies :
  
- L’authentification serveur à serveur Lyss-Exchange doit être configurée.
    
- Les utilisateurs test doivent disposer d’une boîte aux lettres Exchange valide.
    
Une fois ces conditions sont remplies, vous pouvez exécuter l’applet de commande Windows PowerShell suivante pour migrer des listes de contacts des utilisateurs de test vers Exchange :
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

La migration des listes de contacts des utilisateurs test vers Exchange peut prendre un moment. Pour surveiller la progression de la migration, la même ligne de commande peut être exécutée sans-indicateur du programme d’installation :
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Cette ligne de commande aboutira une fois que la migration est terminée.
  
### <a name="xmpp-synthetic-transaction"></a>Transaction synthétique XMPP

La transaction synthétique de messagerie instantanée XMPP (Extensible Messaging and Presence Protocol) requiert que la fonctionnalité XMPP soit configurée avec un ou plusieurs domaines fédérés.
  
Pour activer la transaction synthétique XMPP, vous devez fournir un paramètre XmppTestReceiverMailAddress avec un compte d’utilisateur au niveau d’un domaine XMPP routable. Par exemple :
  
```
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

Dans cet exemple, un Skype pour règle Business Server devrez exister pour router les messages pour litwareinc.com vers une passerelle XMPP.

> [!NOTE]
> XMPP passerelles et les proxys sont disponibles dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. Pour plus d’informations, voir [la fédération XMPP de migration](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Transaction synthétique VIS (Serveur d’interopérabilité vidéo)

La transaction synthétique vidéo Interop Server (pouces) nécessite que vous téléchargez et installez les fichiers de prise en charge les transactions synthétiques ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)). 
  
Pour installer VISSTSupportPackage.msi, assurez-vous que les dépendances (sous Configuration logicielle requise) du msi sont déjà installées. Exécutez VISSTSupportPackage.msi pour effectuer une installation simple. Le fichier .msi installe tous les fichiers dans le chemin d’accès suivant : « %ProgramFiles%\VIS Package de prise en charge des transactions synthétiques ».
  
Pour plus d’informations sur l’exécution de la Transaction synthétique VIS, reportez-vous à la documentation de l’applet de commande [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) .
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Modification de la fréquence d’exécution des transactions synthétiques
<a name="special_synthetictrans"> </a>

Par défaut, les transactions synthétiques s’exécutent avec les utilisateurs configurés toutes les 15 minutes. Les transactions synthétiques sont exécutées en mode séquentiel dans un ensemble d’utilisateurs pour éviter tout conflit entre deux transactions synthétiques. Un intervalle plus long est nécessaire pour laisser à toutes les transactions synthétiques le temps de se terminer.
  
Si vous souhaitez exécuter les transactions synthétiques plus fréquemment, il est conseillé de réduire le nombre de transactions synthétiques exécutées avec un ensemble d’utilisateurs donné afin que les tests puissent se terminer dans le délai imparti en tenant compte de retards occasionnels liés au réseau. Si vous exécutez plus de transactions synthétiques que recommandé, créez plusieurs ensembles d’utilisateurs pour exécuter davantage de transactions synthétiques.
  
Pour modifier la fréquence à laquelle les transactions synthétiques sont exécutées, procédez comme suit :
  
1. Ouvrir System Center Operations Manager. Cliquez sur Création. Cliquez sur règles section (création).
    
2. Dans la section règles, recherchez la règle avec le nom « Main synthétique règle de Collection performances de Transaction canal d’injection ».
    
3. Cliquez avec le bouton droit sur la règle et sélectionnez substitutions, sélectionnez Remplacer la règle, puis sélectionnez « pour tous les objets de classe : Observateur Pool ».
    
4. Dans la fenêtre Propriétés remplacer, sélectionnez le nom du paramètre « Fréquence » et définir la valeur Override à celui souhaité.
    
5. Dans la même fenêtre, sélectionnez le pack d’administration sur lequel cette substitution doit être appliquée.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Utilisation de la journalisation enrichie pour les transactions synthétiques
<a name="special_synthetictrans"> </a>

Les transactions synthétiques se sont révélées extrêmement utiles pour aider les administrateurs à identifier les problèmes du système. Par exemple, l’applet de commande Test-Cs Registration pouvait alerter les administrateurs quand les utilisateurs rencontraient des problèmes pour s’inscrire à Skype Entreprise Server. Cependant, d’autres détails peuvent être nécessaires pour déterminer la cause réelle d’une défaillance.
  
Pour cette raison, les transactions synthétiques fournissent une journalisation enrichie. Avec cette journalisation enrichie, pour chaque activité qu’entreprend une transaction synthétique, les informations suivantes sont enregistrées :
  
- L’heure de début de l’activité.
    
- L’heure de fin de l’activité.
    
- L’action effectuée (par exemple, création, participation ou fin de participation à une conférence, connexion à Skype Entreprise Server, envoi d’un message instantané).
    
- Informatif, détaillé, avertissement ou messages d’erreur générés pendant l’exécution de l’activité.
    
- Les messages d’inscription SIP.
    
- Les enregistrements d’exception ou codes de diagnostic générés pendant l’exécution de l’activité.
    
- Le résultat net suite à l’exécution de l’activité.
    
Ces informations sont automatiquement générées à chaque exécution d’une transaction synthétique. Toutefois, elles ne sont pas automatiquement affichées ou enregistrées dans un fichier journal. Si vous exécutez manuellement une transaction synthétique, vous pouvez utiliser le paramètre OutLoggerVariable pour spécifier une variable Windows PowerShell dans laquelle seront stockées les informations. À partir de là, vous disposez de deux méthodes pour enregistrer et/ou afficher les messages d’erreur dans le journal enrichi au format XML ou HTML. 
  
Pour récupérer les informations de dépannage, spécifiez le paramètre OutLoggerVariable, suivi d’un nom de variable que vous choisissez :
  
```
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> Précéder pas le nom de la variable par le caractère $. Utilisez un nom de variable comme RegistrationTest (et non $RegistrationTest). 
  
Lorsque vous exécutez cette commande, vous obtenez un résultat semblable à celui-ci :
  
Nom de domaine complet cible : atl-cs-001 résultat : Échec de latence : 00:00:00 Message d’erreur : cet ordinateur ne dispose pas de tous les certificats affectés. Diagnostic : vous pouvez accéder à des informations plus détaillées pour cette erreur que simplement le message d’erreur indiqué ici.

Pour obtenir ces informations au format HTML, utilisez une commande de ce type pour enregistrer les informations stockées dans la variable RegistrationTest dans un fichier HTML :
  
```
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Vous pouvez aussi utiliser la méthode ToXML() pour enregistrer les données dans un fichier XML :
  
```
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Vous pouvez afficher ces fichiers à l’aide de Windows Internet Explorer, Microsoft Visual Studio ou toute autre application capable d’ouvrir des fichiers HTML/XML.
  
Exécuter à partir de System Center Operations Manager à l’intérieur de transactions synthétiques génère automatiquement ces fichiers journaux pour les échecs. Toutefois, ces journaux ne sont pas générés si l’exécution échoue avant que Skype Entreprise Server PowerShell n’ait pu charger et exécuter la transaction synthétique. 
  
> [!IMPORTANT]
> Par défaut, Skype pour Business Server enregistre les fichiers journaux dans un dossier qui n’est pas partagé. Pour que ces journaux accessibles, vous devez partager ce dossier. Par exemple : \\atl-watcher-001.litwareinc.com\WatcherNode. 
