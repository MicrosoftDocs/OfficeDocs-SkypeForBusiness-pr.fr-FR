---
title: Configurer les paramètres et les utilisateurs de test de nœuds de l’observeur
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: Configurez les paramètres des comptes d’utilisateur test et des nœuds d’Skype Entreprise Server pour les transactions synthétiques.
ms.openlocfilehash: b01b99136cf8fc8495dbf090b8e1def5f56ff77c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837436"
---
# <a name="skype-for-business-server-configure-watcher-node-test-users-and-settings"></a>Skype Entreprise Server : configurer les paramètres et les utilisateurs de test du nœud de l’observeur
 
**Résumé :** Configurez les paramètres des comptes d’utilisateurs test et des nœuds d’Skype Entreprise Server pour les transactions synthétiques.
  
Après avoir configuré l’ordinateur qui jouera le rôle de nœud observateur, vous devez :
  
1. [Configurez les comptes d’utilisateur test](test-users-and-settings-2019.md#testuser) à utiliser par ces nodes d’observation. SI vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser l’applet de commande **Set-CsTestUserCredential** pour activer ces comptes pour une utilisation sur le nœud observateur ;
    
2. mettre à jour les paramètres de configuration du nœud observateur.
    
## <a name="configure-test-user-accounts"></a>Configurer les comptes d’utilisateur test
<a name="testuser"> </a>

Les comptes test n’ont pas besoin de représenter des personnes réelles, mais ils doivent être des comptes Active Directory valides. En outre, ces comptes doivent être activés pour Skype Entreprise Server, ils doivent avoir des adresses SIP valides et être activés pour Voix Entreprise (pour utiliser la transaction synthétique Test-CsPstnPeerToPeerCall). 
  
Si vous utilisez la méthode d’authentification TrustedServer, il vous suffit de vous assurer que ces comptes existent et de les configurer comme indiqué. Affectez au moins trois utilisateurs de test pour chaque pool que vous souhaitez tester. Si vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser la cmdlet Set-CsTestUserCredential et l’Skype Entreprise Server Management Shell pour permettre à ces comptes de test de fonctionner avec les transactions synthétiques. Pour ce faire, exécutez une commande semblable à la suivante (ces commandes supposent que les trois comptes d’utilisateur Active Directory ont été créés et que ces comptes sont activés pour Skype Entreprise Server) :
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

Incluez non seulement l’adresse SIP, mais également le nom d’utilisateur et le mot de passe. Si vous n’incluez pas le mot de passe, Set-CsTestUserCredential cmdlet vous invite à entrer ces informations. Le nom d’utilisateur peut être spécifié en utilisant le format nom de domaine \nom d’utilisateur indiqué dans le bloc de code précédent.
  
Pour vérifier que les informations d’identification de l’utilisateur test ont été créées, exécutez les commandes Skype Entreprise Server Management Shell :
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

Des informations similaires à ceci sont renvoyées pour chaque utilisateur :
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurer un nœud d’observation de base avec les transactions synthétiques par défaut

Une fois les utilisateurs de test créés, vous pouvez créer un nœud d’observation à l’aide d’une commande semblable à celle-ci :
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

Cette commande crée un nœud observateur qui utilise les paramètres par défaut et exécute le jeu de transactions synthétiques par défaut. Le nouveau nœud observateur utilise également les utilisateurs tests watcher1@litwareinc.com, watcher2@litwareinc.com et watcher3@litwareinc.com. Si le nœud observateur utilise l’authentification TrustedServer, les trois comptes de test peuvent être des comptes d’utilisateur valides activés pour Active Directory et Skype Entreprise Server. Si le nœud observeur utilise la méthode d’authentification Negotiate, ces comptes d’utilisateur doivent également être activés pour le nœud de l'Set-CsTestUserCredential cmdlet.
  
Pour vérifier que la découverte automatique du pool cible pour se connecter est configurée correctement au lieu de cibler un pool directement, utilisez plutôt les étapes suivantes :
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Configuration de tests étendus

Si vous souhaitez activer le test PSTN, qui vérifie la connectivité avec le réseau téléphonique commuté, vous devez faire un peu plus de configuration lors de la configuration du nœud de l’observation. Tout d’abord, vous devez associer vos utilisateurs de test au type de test PSTN en exécutant une commande semblable à celle-ci à partir de Skype Entreprise Server Management Shell :
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Les résultats de cette commande doivent être stockés dans une variable. Dans cet exemple, la variable est nommée $pstnTest. 
  
Ensuite, vous pouvez utiliser l’applet de calcul **New-CsWatcherNodeConfiguration** pour associer le type de test (stocké dans la variable $pstnTest) à un pool Skype Entreprise Server. Par exemple, la commande suivante crée une configuration de nœud d’observation pour la atl-cs-001.litwareinc.com du pool, en ajoutant les trois utilisateurs de test créés précédemment et en ajoutant le type de test PSTN :
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

La commande précédente échoue si vous n’avez pas installé les fichiers principaux Skype Entreprise Server et la base de données RTCLocal sur l’ordinateur du nœud observeur. 
  
Pour tester plusieurs stratégies de voix, vous pouvez créer un test étendu pour chaque stratégie à l’aide de l’cmdlet **New-CsExtendedTest.** Les utilisateurs fournis doivent être configurés avec les stratégies de voix souhaitées. Les tests étendus sont passés à l’applet de la cmdlet **New-CsWatcherNodeConfiguration** à l’aide de délimiteur-virgules, tels que :
  
-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}
  
Étant donné que la cmdlet **New-CsWatcherNodeConfiguration** a été appelée sans utiliser le paramètre Tests, seules les transactions synthétiques par défaut (et la transaction synthétique étendue spécifiée) seront activées pour le nouveau nœud observateur. Par conséquent, le nœud de l’observation testera les composants suivants :
  
- Inscription
    
- IM (Messagerie instantanée)
    
- GroupIM
    
- P2PAV (sessions audio/vidéo d’égal à égal)
    
- AvConference (audioconférence)
    
- Présence
    
- ABS (Service de carnet d’adresses)
    
- ABWQ (Service web de carnet d’adresses)
    
Les composants suivants ne seront pas testés par défaut :
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (Messagerie unifiée Exchange)
    
- JoinLauncher
    
- MCXP2PIM (messagerie instantanée d’appareil mobile hérité)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (appels de passerelle PSTN, spécifiés en tant que test étendu)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>Ajout et suppression de transactions synthétiques

Après avoir configuré un nœud observateur, vous pouvez utiliser l’applet de commande Set-CsWatcherNodeConfiguration pour ajouter ou supprimer des transactions synthétiques du nœud. Par exemple, pour ajouter le test PersistentChatMessage au nœud observateur, utilisez la méthode Add et une commande semblable à la suivante :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

Plusieurs tests peuvent être ajoutés en séparant leur nom par des virgules. Par exemple :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

Une erreur se produit si un ou plusieurs de ces tests (par exemple DataConference) ont déjà été activés sur le nœud de l’observation. Dans ce cas, vous recevrez un message d’erreur semblable au message suivant :
  
Set-CsWatcherNodeConfiguration : il existe une séquence de touches en double « DataConference » pour « urn:schema:Microsoft.Rtc.Management ». Paramètres. Clé watcherNode.2010:TestName ou contrainte d’identité unique.
  
Lorsque cette erreur se produit, aucune modification n’est appliquée. La commande doit être réexécutée en supprimant le test dupliqué.
  
Pour supprimer une transaction synthétique d’un nœud d’observation, utilisez la méthode Remove. Par exemple, la commande suivante supprime le test ABWQ d’un nœud observateur :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Vous pouvez utiliser la méthode Replace pour remplacer tous les tests actuellement activés par un ou plusieurs nouveaux tests. Par exemple, si vous souhaitez qu’un nœud observeur exécute uniquement le test de messagerie instantanée, vous pouvez le configurer à l’aide de cette commande :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Lorsque vous exécutez cette commande, toutes les transactions synthétiques sur le nœud d’observation spécifié sont désactivées à l’exception de la messagerie instantanée.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Affichage et test de la configuration du nœud observateur

Si vous souhaitez afficher les tests qui ont été affectés à un nœud d’observation, utilisez une commande semblable à celle-ci :
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Cette commande retourne des informations semblables aux suivantes, selon les transactions synthétiques qui ont été affectées au nœud :
  
Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference
> [!TIP]
> Pour afficher les transactions synthétiques par ordre alphabétique, exécutez plutôt la commande suivante : 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Pour vérifier qu’un nœud d’observation a été créé, tapez la commande suivante à partir Skype Entreprise Server Management Shell :
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Vous recevez des informations semblables à ceci :
  
Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...} ExtendedTests : {TestUsers=IList<System.String>; Name=PSTN Test; Te...} TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061 Pour vérifier que le nœud d’observation a été configuré correctement, tapez la commande suivante à partir de Skype Entreprise Server Management Shell :
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Cette commande teste chaque nœud de l’analyseur dans votre déploiement et confirme si les actions suivantes sont terminées :
  
- Le rôle de bureau d’enregistrement requis est installé
    
- La clé de Registre requise est créée (terminée lorsque vous avez Set-CsWatcherNodeConfiguration cmdlet)
    
- Vos serveurs exécutent la version correcte de Skype Entreprise Server
    
- Vos ports sont configurés correctement
    
- Vos utilisateurs de test affectés ont les informations d’identification requises
    
## <a name="managing-watcher-nodes"></a>Gestion des nœuds observateurs
<a name="testuser"> </a>

En plus de modifier les transactions synthétiques qui sont exécutées sur un nœud observateur, vous pouvez également utiliser l’applet de calcul **Set-CsWatcherNodeConfiguration** pour effectuer deux autres tâches importantes : l’activation et la désactivation du nœud observateur et la configuration du nœud observateur pour qu’il utilise des URL Web internes ou externes lors de l’exécution de ses tests.
  
Par défaut, les nœuds observateur sont conçus pour exécuter régulièrement toutes leurs transactions synthétiques activées. Toutefois, vous pouvez parfois suspendre ces transactions. Par exemple, si le nœud observateur est temporairement déconnecté du réseau, il est inutile d’exécuter les transactions synthétiques. Sans connectivité réseau, ces transactions échoueront. Pour désactiver temporairement un nœud d’observation, exécutez une commande semblable à celle-ci à partir de Skype Entreprise Server Management Shell :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Cette commande désactive l’exécution des transactions synthétiques sur le nœud de l'001.litwareinc.com. Pour reprendre l’exécution des transactions synthétiques, affectez à la propriété Enabled la valeur True ($True) :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> La propriété Enabled peut être utilisée pour activer ou désactiver les nœuds observateur. Si vous souhaitez supprimer définitivement un nœud observateur, utilisez l’applet de commande **Remove-CsWatcherNodeConfiguration** :
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Cette commande supprime tous les paramètres de configuration du nœud de l’ordinateur spécifié, ce qui empêche cet ordinateur d’exécution automatique des transactions synthétiques. Toutefois, la commande ne désinstalle pas les fichiers System Center’agent ou les Skype Entreprise Server système.
  
Par défaut, les nodes d’observeur utilisent les URL web externes d’une organisation lors de la conduite de tests. Toutefois, les nodes d’observation peuvent également être configurés pour utiliser les URL Web internes de l’organisation. Cela permet aux administrateurs de vérifier l’accès URL pour les utilisateurs situés à l’intérieur du réseau de périmètre. Pour configurer un nœud d’observation afin qu’il utilise des URL internes au lieu d’URL externes, définissez la propriété UseInternalWebURls sur True ($True) :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

La réinitialisation de cette propriété sur la valeur par défaut false ($False) entraîne une nouvelle utilisation des URL externes par l’observeur :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Instructions d’installation spéciales pour les transactions synthétiques
<a name="special_synthetictrans"> </a>

La plupart des transactions synthétiques peuvent s’exécuter sur un nœud d’observation tel qu’il est. Dans la plupart des cas, dès que la transaction synthétique est ajoutée aux paramètres de configuration du nœud de l’analyseur, le nœud de l’analyseur peut commencer à utiliser cette transaction synthétique lors de ses tests. Toutefois, certaines transactions synthétiques nécessitent des instructions d’installation spéciales, comme expliqué dans les sections suivantes.
  
### <a name="data-conferencing-synthetic-transaction"></a>Transaction synthétique de conférence de données

Si votre ordinateur de nœud observeur se trouve en dehors de votre réseau de périmètre, vous ne serez probablement pas en mesure d’exécuter la transaction synthétique de conférence de données, sauf si vous désactivez d’abord les paramètres proxy du navigateur Internet Windows Internet Explorer® pour le compte de service réseau en effectuant les étapes suivantes :
  
1. Sur l’ordinateur du nœud observeur, cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Accessoires,** sur Invite de **commandes,** puis cliquez sur Exécuter **en tant qu’administrateur.**
    
2. Dans la fenêtre de console, tapez la commande suivante, puis appuyez sur Entrée. 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

Le message suivant s’affiche dans la fenêtre de commande :
  
BITSAdmin est supprimé et il n’est pas garanti qu’il soit disponible dans les versions futures de Windows. Les outils d’administration du service BITS sont désormais fournis par les cmdlets BITS PowerShell.
  
Paramètres de proxy Internet pour le compte NetworkService définies sur NO_PROXY. 
  
(connection = valeur par défaut)
  
Ce message indique que vous avez désactivé les paramètres proxy Internet Explorer pour le compte de service réseau.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange Transaction synthétique de messagerie unifiée

La transaction synthétique Exchange de messagerie unifiée vérifie que les utilisateurs de test peuvent se connecter aux comptes de messagerie vocale Exchange.
  
Les utilisateurs de test doivent être préconfigurés avec des comptes de messagerie vocale. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Transaction synthétique de conversation permanente

Pour utiliser la transaction synthétique de conversation permanente, vous devez d’abord créer un canal et accorder aux utilisateurs de test les autorisations de l’utiliser.
  
Vous pouvez utiliser la transaction synthétique de conversation permanente pour configurer ce canal : 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Exécutez cette tâche de configuration à partir de l’entreprise :
  
- S’il est exécuté à partir d’un ordinateur autre que le serveur, l’utilisateur qui exécute l'; doit être membre du rôle CsPersistentChatAdministrators pour le contrôle d’accès Role-Based (RBAC).
    
- S’il est exécuté à partir du serveur lui-même, l’utilisateur qui exécute la cmdlet doit être membre du groupe RTCUniversalServerAdmins.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Transaction synthétique d’appel PSTN D’égal à égal

La Test-CsPstnPeerToPeerCall synthétique vérifie la possibilité de passer et de recevoir des appels via un réseau téléphonique commuté (PSTN).
  
Pour exécuter cette transaction synthétique, vous devez configurer :
  
- Deux utilisateurs de test à UC (un appelant et un récepteur).
    
- Numéros de sélection directe à l’arrivée (SDA) pour chaque compte d’utilisateur
    
- Stratégies VoIP et itinéraires de voix qui permettent aux appels vers le numéro du destinataire d’atteindre la passerelle PSTN.
    
- Passerelle PSTN qui accepte les appels et les médias qui routent les appels vers le pool d’accueil d’un récepteur, en fonction du numéro composé.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Transaction synthétique du magasin de contacts unifié

La transaction synthétique du magasin de contacts unifié vérifie la capacité des utilisateurs Skype Entreprise Server récupérer des contacts pour le compte d’un utilisateur à partir Exchange.
  
Pour utiliser cette transaction synthétique, les conditions suivantes doivent être remplies :
  
- Lyss-Exchange'authentification de serveur à serveur doit être configurée.
    
- Les utilisateurs test doivent avoir une boîte aux lettres Exchange valide.
    
Une fois ces conditions remplies, vous pouvez exécuter la cmdlet Windows PowerShell suivante pour migrer les listes de contacts des utilisateurs de test vers Exchange :
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

La migration des listes de contacts des utilisateurs de test vers Exchange peut prendre un certain temps. Pour surveiller la progression de la migration, vous pouvez exécuter la même ligne de commande sans l’indicateur -Setup :
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Cette ligne de commande réussit une fois la migration terminée.
  
### <a name="xmpp-synthetic-transaction"></a>Transaction synthétique XMPP

La transaction synthétique de messagerie instantanée XMPP (Extensible Messaging and Presence Protocol) nécessite que vous configuriez la fonctionnalité XMPP avec un ou plusieurs domaines fédérés.
  
Pour activer la transaction synthétique XMPP, vous devez fournir un paramètre XmppTestReceiverMailAddress avec un compte d’utilisateur dans un domaine XMPP routable. Par exemple :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

Dans cet exemple, une règle Skype Entreprise Server doit exister pour router les messages litwareinc.com vers une passerelle XMPP.

> [!NOTE]
> Les passerelles et les proxies XMPP étaient disponibles dans Skype Entreprise Server 2015, mais ne sont plus pris en charge dans Skype Entreprise Server 2019. Pour [plus d’informations, voir](../migration/migrating-xmpp-federation.md) Migration de la fédération XMPP.
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Transaction synthétique VIS (Video Interop Server)

La transaction synthétique VIS (Video Interop Server) nécessite de télécharger et d’installer les fichiers de prise en charge des transactions synthétiques ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)). 
  
Pour installer VISSTSupportPackage.msi, assurez-vous que les dépendances (sous System Requirements) pour le msi sont déjà installées. Exécutez VISSTSupportPackage.msi pour une installation simple. Le .msi installe tous les fichiers dans le chemin d’accès suivant : « %ProgramFiles%\VIS Synthetic Transaction Support Package ».
  
Pour plus d’informations sur l’exécuter, reportez-vous à la documentation de l’cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV.](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV)
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Modification de la fréquence d’utilisation des transactions synthétiques
<a name="special_synthetictrans"> </a>

Par défaut, les transactions synthétiques s’exécutent avec les utilisateurs configurés toutes les 15 minutes. Les transactions synthétiques sont exécutés séquentiellement au sein d’un ensemble d’utilisateurs afin d’éviter que deux transactions synthétiques entrent en conflit. Un intervalle plus long est nécessaire pour que toutes les transactions synthétiques se terminent.
  
S’il est souhaitable d’exécuter des transactions synthétiques plus fréquemment, le nombre de transactions synthétiques qui s’exécutent avec un ensemble donné d’utilisateurs doit être réduit afin que les tests se terminent dans la plage de temps souhaitée avec une certaine mémoire tampon pour les retards occasionnels du réseau. Si l’exécution de transactions synthétiques est souhaitable, créez davantage de jeux d’utilisateurs pour exécuter davantage de transactions synthétiques.
  
Pour modifier la fréquence à laquelle les transactions synthétiques s’exécutent, suivez les étapes suivantes :
  
1. Ouvrez System Center Operations Manager. Cliquez sur La section Auteur. Section Règles de clic (sous Auteur)
    
2. Dans la section Règles, recherchez la règle avec le nom « Main Synthetic Transaction Runner Performance Collection Rule »
    
3. Cliquez avec le bouton droit sur la règle, puis sélectionnez Remplacements, sélectionnez Remplacer la règle, puis sélectionnez « Pour tous les objets de la classe : Pool Watcher »
    
4. Dans la fenêtre Remplacer les propriétés, sélectionnez le nom du paramètre « Frequency » et définissez la valeur de remplacement sur la valeur souhaitée.
    
5. Dans la même fenêtre, sélectionnez le pack d’administration auquel ce remplacement doit être appliqué.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Utilisation de la journalisation enrichie pour les transactions synthétiques
<a name="special_synthetictrans"> </a>

Les transactions synthétiques sont utiles pour aider à identifier les problèmes avec le système. Par exemple, la cmdlet Test-CsRegistration peut alerter les administrateurs du fait que les utilisateurs avaient des difficultés à s’inscrire auprès Skype Entreprise Server. Toutefois, des détails plus détaillés peuvent être nécessaires pour déterminer la cause réelle d’une défaillance.
  
Pour cette raison, les transactions synthétiques fournissent une journalisation enrichie. Avec la journalisation enrichie, pour chaque activité entreprise par une transaction synthétique, les informations suivantes sont enregistrées :
  
- Heure de début de l’activité.
    
- Heure de fin de l’activité.
    
- Action effectuée (par exemple, création, adhésion ou sortie d’une conférence, Skype Entreprise Server et envoi d’un message instantané).
    
- Les messages informatifs, détaillés, d’avertissement ou d’erreur générés pendant l’exécution de l’activité
    
- Messages d’inscription SIP.
    
- Enregistrements d’exception ou codes de diagnostic générés lors de l’activité.
    
- Résultat net de l’exécution de l’activité.
    
Ces informations sont générées automatiquement chaque fois qu’une transaction synthétique est exécuté, mais ne sont pas automatiquement affichées ou enregistrées dans un fichier journal. Si vous exécutez manuellement une transaction synthétique, vous pouvez utiliser le paramètre OutLoggerVariable pour spécifier une variable Windows PowerShell dans laquelle les informations seront stockées. À partir de là, vous avez la possibilité d’utiliser l’une des deux méthodes pour enregistrer et/ou afficher les messages d’erreur dans le journal enrichi au format XML ou HTML. 
  
Pour récupérer les informations de dépannage, spécifiez le paramètre OutLoggerVariable, suivi d’un nom de variable que vous choisissez :
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> : ne faites pas préfacer le nom de la variable avec le caractère $. Utilisez un nom de variable tel que RegistrationTest (pas $RegistrationTest). 
  
Lorsque vous exécutez cette commande, vous verrez une sortie semblable à celle-ci :
  
Fqdn cible : atl-cs-001.litwareinc.com résultat : Latence d’échec : 00:00:00 Message d’erreur : cet ordinateur ne atl-cs-001.litwareinc.com aucun certificat affecté. Diagnostic : vous pouvez accéder à des informations beaucoup plus détaillées sur cet échec que le simple message d’erreur affiché ici. Pour accéder à ces informations au format HTML, utilisez une commande semblable à celle-ci pour enregistrer les informations stockées dans la variable RegistrationTest dans un fichier HTML :
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Vous pouvez aussi utiliser la méthode ToXML() pour enregistrer les données dans un fichier XML :
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Vous pouvez afficher ces fichiers à l’aide Windows Internet Explorer, Microsoft Visual Studio application ou toute autre application capable d’ouvrir des fichiers HTML/XML.
  
Les transactions synthétiques s’exécutent à System Center Operations Manager génère automatiquement ces fichiers journaux en cas d’échec. Ces journaux ne sont pas générés si l’exécution échoue avant Skype Entreprise Server PowerShell est en mesure de charger et d’exécuter la transaction synthétique. 
  
> [!IMPORTANT]
> Par défaut, Skype Entreprise Server enregistre les fichiers journaux dans un dossier qui n’est pas partagé. Pour rendre ces journaux facilement accessibles, vous devez partager ce dossier. Par exemple : \\ atl-watcher-001.litwareinc.com\WatcherNode.
