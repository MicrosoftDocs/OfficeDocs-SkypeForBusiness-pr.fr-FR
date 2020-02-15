---
title: Configuration des paramètres et des utilisateurs test du nœud observateur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 'Résumé : configurez les comptes d’utilisateur test et les paramètres du nœud observateur pour les transactions synthétiques de Skype entreprise Server.'
ms.openlocfilehash: 8b586cf4c1d003bb54afa050469a10eee8d113e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005949"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Configuration des paramètres et des utilisateurs test du nœud observateur
 
**Résumé :** Configurez des comptes d’utilisateurs test et des paramètres de nœud observateur pour les transactions synthétiques de Skype entreprise Server.
  
Après avoir configuré l’ordinateur qui jouera le rôle de nœud observateur, vous devez :
  
1. [Configurez des comptes d’utilisateurs test](test-users-and-settings.md#testuser) devant être utilisés par ces nœuds observateurs. SI vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser l’applet de commande **Set-CsTestUserCredential** pour activer ces comptes pour une utilisation sur le nœud observateur ;
    
2. mettre à jour les paramètres de configuration du nœud observateur.
    
## <a name="configure-test-user-accounts"></a>Configurer des comptes d’utilisateurs test
<a name="testuser"> </a>

Les comptes de test n’ont pas besoin de représenter des personnes réelles, mais ils doivent être des comptes Active Directory valides. En outre, ces comptes doivent être activés pour Skype entreprise Server, doivent avoir des adresses SIP valides, et ils doivent être activés pour voix entreprise (pour utiliser la transaction synthétique test-CsPstnPeerToPeerCall). 
  
Si vous utilisez la méthode d’authentification TrustedServer, tout ce que vous devez faire est de vous assurer que ces comptes existent et de les configurer comme indiqué. Vous devez affecter au moins deux utilisateurs de test pour chaque pool que vous souhaitez tester. Si vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser la cmdlet Set-applet cstestusercredential et Skype for Business Server Management Shell pour permettre à ces comptes de test de fonctionner avec les transactions synthétiques. Pour ce faire, exécutez une commande semblable à la suivante (ces commandes partent du principe que les deux comptes d’utilisateur Active Directory ont été créés et que ces comptes sont activés pour Skype entreprise Server) :
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

Vous devez inclure non seulement l’adresse SIP, mais également le nom d’utilisateur et le mot de passe. Si vous n’incluez pas le mot de passe, l’applet de commande Set-applet cstestusercredential vous invite à entrer ces informations. Le nom d’utilisateur peut être spécifié à l’aide du format de nom de DOMAINE\nom d’utilisateur indiqué dans le bloc de code précédent.
  
Pour vérifier que les informations d’identification de l’utilisateur de test ont été créées, exécutez les commandes suivantes à partir de Skype entreprise Server Management Shell :
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

Des informations semblables à ce qui suit sont renvoyées pour chaque utilisateur :
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System. Security. SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configuration d’un nœud observateur de base avec les transactions synthétiques par défaut

Une fois que les utilisateurs de test ont été créés, vous pouvez créer un nœud observateur à l’aide d’une commande semblable à celle-ci :
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

Cette commande crée un nœud observateur qui utilise les paramètres par défaut et exécute le jeu de transactions synthétiques par défaut. Le nouveau nœud observateur utilise également les utilisateurs test watcher1@litwareinc.com et watcher2@litwareinc.com. Si le nœud observateur utilise l’authentification TrustedServer, les deux comptes de test peuvent être des comptes d’utilisateurs valides activés pour Active Directory et Skype entreprise Server. Si le nœud observateur utilise la méthode d’authentification Negotiate, ces comptes d’utilisateur doivent également être activés pour le nœud observateur à l’aide de la cmdlet Set-applet cstestusercredential.
  
Pour vérifier que la découverte automatique du pool cible pour la connexion est correctement configurée plutôt que de cibler un pool, suivez plutôt ces étapes :
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Configuration de tests étendus

Si vous souhaitez activer le test PSTN, qui vérifie la connectivité avec le réseau téléphonique commuté public, vous devez effectuer une configuration supplémentaire lors de la configuration du nœud observateur. Tout d’abord, vous devez associer vos utilisateurs de test au type de test PSTN en exécutant une commande semblable à celle-ci à partir de Skype entreprise Server Management Shell :
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Les résultats de cette commande doivent être stockés dans une variable. Dans cet exemple, la variable est nommée $pstnTest. 
  
Ensuite, vous pouvez utiliser la cmdlet **New-applet cswatchernodeconfiguration** pour associer le type de test (stocké dans la variable $pstnTest) à un pool Skype entreprise Server. Par exemple, la commande suivante crée une nouvelle configuration de nœud observateur pour le pool atl-cs-001.litwareinc.com, ajoutant les deux utilisateurs test créés précédemment et en ajoutant le type de test PSTN :
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

La commande précédente échoue si vous n’avez pas installé les fichiers principaux de Skype entreprise Server et la base de données RTCLocal sur l’ordinateur du nœud observateur. 
  
Pour tester plusieurs stratégies de voix, vous pouvez créer un test étendu pour chaque stratégie à l’aide de la cmdlet **New-CsExtendedTest** . Les utilisateurs fournis doivent être configurés avec les stratégies de voix souhaitées. Les tests étendus sont transmis à la cmdlet **New-applet cswatchernodeconfiguration** à l’aide de délimiteurs par des virgules, tels que :
  
-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}
  
Étant donné que la cmdlet **New-applet cswatchernodeconfiguration** a été appelée sans utiliser le paramètre tests, seules les transactions synthétiques par défaut (et la transaction synthétique étendue spécifiée) seront activées pour le nouveau nœud observateur. Par conséquent, le nœud observateur testera les composants suivants :
  
- Son
    
- IM (Messagerie instantanée)
    
- GroupIM
    
- P2PAV (sessions audio/vidéo d’égal à égal)
    
- AvConference (audioconférence)
    
- Présence
    
- ABS (Service de carnet d’adresses)
    
- ABWQ (Service web de carnet d’adresses)
    
Les composants suivants ne seront pas testés par défaut :
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (Messagerie unifiée Exchange)
    
- JoinLauncher
    
- MCXP2PIM (messagerie instantanée de l’appareil mobile hérité)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- Appels de la passerelle PSTN (RTC), spécifié comme un test étendu
    
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

Une erreur se produit si un ou plusieurs de ces tests (par exemple, DataConference) ont déjà été activés sur le nœud observateur. Dans ce cas, vous recevez un message d’erreur semblable au suivant :
  
Set-applet cswatchernodeconfiguration : il existe une combinaison de clés dupliquée « DataConference » pour la clé « urn : Schema : Microsoft. RTC. Management. Settings. WatcherNode. 2010 : nomtest » ou une contrainte d’identité unique.
  
Lorsque cette erreur se produit, aucune modification n’est appliquée. La commande doit être réexécutée avec le test en double supprimé.
  
Pour supprimer une transaction synthétique d’un nœud observateur, utilisez la méthode Remove. Par exemple, la commande suivante supprime le test ABWQ d’un nœud observateur :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Vous pouvez utiliser la méthode Replace pour remplacer tous les tests actuellement activés par un ou plusieurs nouveaux tests. Par exemple, si vous souhaitez qu’un nœud observateur exécute uniquement le test de messagerie instantanée, vous pouvez configurer ce dernier à l’aide de la commande suivante :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Lorsque vous exécutez cette commande, toutes les transactions synthétiques sur le nœud observateur spécifié sont désactivées, à l’exception de la messagerie instantanée.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Affichage et test de la configuration du nœud observateur

Si vous souhaitez afficher les tests qui ont été assignés à un nœud observateur, exécutez une commande semblable à la suivante :
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Cette commande renvoie des informations semblables à celles-ci, en fonction des transactions synthétiques qui ont été affectées au nœud :
  
Inscription de messagerie instantanée GroupIM P2PAV AvConference présence PersistentChatMessage DataConference
> [!TIP]
> Pour afficher les transactions synthétiques par ordre alphabétique, exécutez plutôt la commande suivante : 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Pour vérifier qu’un nœud observateur a été créé, tapez la commande suivante à partir de Skype entreprise Server Management Shell :
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Vous obtiendrez des informations semblables à celles-ci :
  
Identity : atl-cs-001.litwareinc.com <br/>
TestUsers : {sip :watcher1@litwareinc.com, sip :watcher2@litwareinc.com...}<br/>
ExtendedTests : {TestUsers = IList<System. String> ; Nom = test PSTN ; Te...}<br/>
TargetFqdn : atl-cs-001.litwareinc.com<br/>
Numéro_port : 5061<br/>

Pour vérifier que le nœud observateur a été correctement configuré, tapez la commande suivante à partir de Skype entreprise Server Management Shell :
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Cette commande teste chaque nœud observateur de votre déploiement et confirme si les actions suivantes sont effectuées :
  
- Le rôle serveur d’inscriptions requis est installé.
    
- La clé de registre requise est créée (terminée lorsque vous avez exécuté la cmdlet Set-applet cswatchernodeconfiguration).
    
- Vos serveurs exécutent la version correcte de Skype entreprise Server.
    
- Vos ports sont configurés correctement.
    
- si vos utilisateurs de test assignés disposent des informations d’identification requises.
    
## <a name="managing-watcher-nodes"></a>Gestion des nœuds observateurs
<a name="testuser"> </a>

En plus de modifier les transactions synthétiques qui sont exécutées sur un nœud observateur, vous pouvez également utiliser la cmdlet **Set-applet cswatchernodeconfiguration** pour effectuer deux autres tâches importantes : l’activation et la désactivation du nœud observateur, et la configuration du nœud observateur pour utiliser des URL Web internes ou des URL Web externes lors de l’exécution de ses tests.
  
Par défaut, les nœuds observateur sont conçus pour exécuter régulièrement toutes leurs transactions synthétiques activées. Toutefois, il peut arriver que vous souhaitiez suspendre ces transactions. Par exemple, si le nœud observateur est temporairement déconnecté du réseau, il est inutile d’exécuter les transactions synthétiques. Sans connectivité réseau, ces transactions échouent. Pour désactiver temporairement un nœud observateur, exécutez une commande semblable à celle-ci à partir de Skype entreprise Server Management Shell :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Cette commande désactive l’exécution des transactions synthétiques sur le nœud observateur ATL observateur 001.litwareinc.com. Pour reprendre l’exécution des transactions synthétiques, affectez à la propriété Enabled la valeur True ($True) :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> La propriété Enabled peut être utilisée pour activer ou désactiver les nœuds observateur. Si vous souhaitez supprimer définitivement un nœud observateur, utilisez l’applet de commande **Remove-CsWatcherNodeConfiguration** :
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Cette commande supprime tous les paramètres de configuration du nœud observateur de l’ordinateur spécifié, ce qui empêche cet ordinateur d’exécuter automatiquement des transactions synthétiques. Toutefois, la commande ne désinstalle pas les fichiers de l’agent System Center ni les fichiers système de Skype entreprise Server.
  
Par défaut, les nœuds observateurs utilisent les URL Web externes d’une organisation lors de la réalisation de tests. Toutefois, les nœuds observateurs peuvent également être configurés pour utiliser les URL Web internes de l’organisation. Cela permet aux administrateurs de vérifier l’accès URL pour les utilisateurs situés à l’intérieur du réseau de périmètre. Pour configurer un nœud observateur afin qu’il utilise des URL internes au lieu d’URL externes, définissez la propriété UseInternalWebURls sur true ($True) :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

La réinitialisation de cette propriété à la valeur par défaut false ($False) fera en sorte que l’observateur utilise de nouveau les URL externes :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Instructions d’installation spéciales pour les transactions synthétiques
<a name="special_synthetictrans"> </a>

La plupart des transactions synthétiques peuvent s’exécuter sur un nœud observateur tel quel. Dans la plupart des cas, dès que la transaction synthétique est ajoutée aux paramètres de configuration du nœud observateur, le nœud observateur peut commencer à utiliser cette transaction synthétique lors de son test. Toutefois, il existe des transactions synthétiques qui nécessitent des instructions de configuration spécifiques, comme indiqué dans les sections suivantes.
  
### <a name="data-conferencing-synthetic-transaction"></a>Transaction synthétique de conférence de données

Si votre ordinateur nœud observateur se trouve en dehors de votre réseau de périmètre, vous ne pourrez probablement pas exécuter la transaction synthétique de conférence de données, sauf si vous avez d’abord désactivé les paramètres de proxy du navigateur Internet® Windows Internet Explorer pour le réseau. Compte de service en procédant comme suit :
  
1. Sur l’ordinateur nœud observateur, cliquez sur **Démarrer**, **sur tous les programmes**, sur **accessoires**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**.
    
2. Dans la fenêtre de la console, tapez la commande suivante, puis appuyez sur entrée. 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    Le message suivant s’affiche dans la fenêtre de commande :

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    Ce message indique que vous avez désactivé les paramètres de proxy Internet Explorer pour le compte service réseau.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Transaction synthétique de la messagerie unifiée Exchange

La transaction synthétique de messagerie unifiée Exchange vérifie que les utilisateurs de test peuvent se connecter aux comptes de messagerie instantanée hébergés dans Exchange.
  
Les utilisateurs test doivent être préconfigurés avec des comptes de messagerie vocale. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Transaction synthétique de conversation permanente

Pour utiliser la transaction synthétique de conversation permanente, vous devez d’abord créer un canal et donner aux utilisateurs test les autorisations pour l’utiliser.
  
Vous pouvez utiliser la transaction synthétique de conversation permanente pour configurer ce canal : 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Vous devez exécuter cette tâche de configuration doit être exécutée à partir de l’intérieur de l’entreprise :
  
- Si elle est exécutée à partir d’un ordinateur non-serveur, l’utilisateur qui exécute l’applet de commande doit être membre du rôle CsPersistentChatAdministrators pour le contrôle d’accès basé sur un rôle (RBAC).
    
- Si elle est exécutée à partir du serveur lui-même, l’utilisateur qui exécute l’applet de commande doit être membre du groupe RTCUniversalServerAdmins.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Transaction synthétique des appels d’égal à égal PSTN

La transaction synthétique test-CsPstnPeerToPeerCall vérifie la capacité de passer et de recevoir des appels via un réseau téléphonique commuté (PSTN).
  
Pour exécuter cette transaction synthétique, vous devez configurer les éléments suivants :
  
- Deux utilisateurs de test à UC activée (un appelant et un récepteur).
    
- Numéros de sélection directe à l’arrivée (SDA) pour chaque compte d’utilisateur
    
- Les stratégies VoIP et les itinéraires des communications vocales qui permettent aux appels au numéro du récepteur d’atteindre la passerelle PSTN.
    
- Une passerelle PSTN qui accepte les appels et les médias qui acheminent les appels vers le pool d’accueil d’un récepteur en fonction du numéro composé.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Transaction synthétique du magasin de contacts unifié

La transaction synthétique du magasin de contacts unifié vérifie la capacité de Skype entreprise Server à récupérer des contacts au nom d’un utilisateur à partir d’Exchange.
  
Pour utiliser cette transaction synthétique, les conditions suivantes doivent être remplies :
  
- Lyss-l’authentification Exchange Server to Server doit être configurée.
    
- Les utilisateurs test doivent disposer d’une boîte aux lettres Exchange valide.
    
Une fois ces conditions remplies, vous pouvez exécuter l’applet de commande Windows PowerShell suivante pour migrer les listes de contacts des utilisateurs test vers Exchange :
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

La migration des listes de contacts de l’utilisateur test vers Exchange peut prendre un certain temps. Pour surveiller la progression de la migration, la même ligne de commande peut être exécutée sans l’indicateur-Setup :
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Cette ligne de commande réussit une fois la migration terminée.
  
### <a name="xmpp-synthetic-transaction"></a>Transaction synthétique XMPP

La transaction synthétique de messagerie électronique XMPP (extensible Messaging and Presence Protocol) exige que vous configuriez la fonctionnalité XMPP avec un ou plusieurs domaines fédérés.
  
Pour activer la transaction synthétique XMPP, vous devez fournir un paramètre XmppTestReceiverMailAddress avec un compte d’utilisateur dans un domaine XMPP routable. Par exemple :
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

Dans cet exemple, une règle de Skype entreprise Server doit exister pour router les messages pour litwareinc.com vers une passerelle XMPP.

> [!NOTE]
> Les passerelles XMPP et les proxys sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019. Pour plus d’informations, consultez la rubrique migration de la [Fédération XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Transaction synthétique de serveur d’interopérabilité vidéo (VIS)

La transaction synthétique VIS (Video Interop Server) requiert le téléchargement et l’installation des fichiers de prise en charge des transactions synthétiques ([VISSTSupportPackage. msi](https://www.microsoft.com/download/details.aspx?id=46921)). 
  
Pour installer VISSTSupportPackage. msi, assurez-vous que les dépendances (sous Configuration système requise) pour le MSI sont déjà installées. Exécutez VISSTSupportPackage. msi pour effectuer une installation simple. Le fichier. msi installe tous les fichiers dans le chemin d’accès suivant : « package de prise en charge des transactions synthétiques%ProgramFiles%\VIS ».
  
Pour plus d’informations sur la façon d’exécuter la transaction synthétique VIS, reportez-vous à la documentation de la cmdlet [test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) .
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Modification de la fréquence d’exécution des transactions synthétiques
<a name="special_synthetictrans"> </a>

Par défaut, les transactions synthétiques sont exécutées avec les utilisateurs configurés toutes les 15 minutes. Les transactions synthétiques sont exécutées de manière séquentielle au sein d’un ensemble d’utilisateurs afin d’éviter que deux transactions synthétiques ne soient en conflit. Un intervalle plus long est nécessaire pour fournir le temps nécessaire à l’exécution de toutes les transactions synthétiques.
  
S’il est souhaitable d’exécuter des transactions synthétiques plus fréquemment, le nombre de transactions synthétiques exécutées avec un ensemble d’utilisateurs donné doit être réduit afin que les tests puissent se terminer dans la plage de temps souhaitée avec une mémoire tampon pour les retards réseau occasionnels. Si l’exécution de transactions synthétiques est souhaitable, créez davantage d’utilisateurs pour exécuter des transactions synthétiques supplémentaires.
  
Pour modifier la fréquence d’exécution des transactions synthétiques, procédez comme suit :
  
1. Ouvrez System Center Operations Manager. Cliquez sur section Création. Cliquez sur la section règles (sous création).
    
2. Dans la section règles, recherchez la règle nommée « principale règle de collecte de performances de transaction de synthèse de transactions synthétiques ».
    
3. Cliquez avec le bouton droit sur la règle, puis sélectionnez remplacer, sélectionnez remplacer la règle, puis « pour tous les objets de la classe : observateur de pools ».
    
4. Dans la fenêtre Propriétés de remplacement, sélectionnez le nom du paramètre « fréquence » et définissez la valeur de remplacement sur l’option souhaitée.
    
5. Dans la même fenêtre, sélectionnez le pack d’administration auquel ce remplacement doit être appliqué.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Utilisation de la journalisation enrichie pour les transactions synthétiques
<a name="special_synthetictrans"> </a>

Les transactions synthétiques se révèlent extrêmement utiles pour vous aider à identifier les problèmes liés au système. Par exemple, l’applet de commande test-CsRegistration pourrait alerter les administrateurs du fait que les utilisateurs ont des difficultés à s’inscrire auprès de Skype entreprise Server. Toutefois, des détails supplémentaires peuvent être nécessaires pour déterminer la cause réelle d’une défaillance.
  
Pour cette raison, les transactions synthétiques fournissent une journalisation enrichie. Avec une journalisation enrichie, pour chaque activité qu’une transaction synthétique s’exécute, les informations suivantes sont enregistrées :
  
- Heure à laquelle l’activité a commencé.
    
- Heure à laquelle l’activité est terminée.
    
- Action effectuée (par exemple, la création, la participation ou la fermeture d’une conférence ; connexion à Skype entreprise Server, envoi d’un message instantané).
    
- Messages informatifs, détaillés, d’avertissement ou d’erreur générés lors de l’exécution de l’activité.
    
- Messages d’inscription SIP.
    
- Les enregistrements d’exception ou les codes de diagnostic générés lors de l’exécution de l’activité.
    
- Résultat net de l’exécution de l’activité.
    
Ces informations sont générées automatiquement chaque fois qu’une transaction synthétique est exécutée, mais elle n’est pas automatiquement affichée ou enregistrée dans un fichier journal. Si vous exécutez manuellement une transaction synthétique, vous pouvez utiliser le paramètre OutLoggerVariable pour spécifier une variable Windows PowerShell dans laquelle les informations seront stockées. À partir de là, vous pouvez utiliser l’une des deux méthodes pour enregistrer et/ou afficher les messages d’erreur dans le journal enrichi au format XML ou HTML. 
  
Pour récupérer les informations de résolution des problèmes, spécifiez le paramètre OutLoggerVariable, suivi d’un nom de variable que vous choisissez :
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> Ne faites pas précéder le nom de variable du caractère $. Utilisez un nom de variable comme RegistrationTest (non $RegistrationTest). 
  
Lorsque vous exécutez cette commande, vous obtiendrez une sortie semblable à ceci :
  
Nom de domaine complet cible : résultat atl-cs-001.litwareinc.com : latence des échecs : message d’erreur 00:00:00 : cet ordinateur ne dispose d’aucun certificat attribué. Diagnostic : vous pouvez accéder à des informations bien plus détaillées sur ce problème que le message d’erreur affiché ici.

Pour accéder à ces informations au format HTML, utilisez une commande semblable à celle-ci pour enregistrer les informations stockées dans la variable RegistrationTest dans un fichier HTML :
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Vous pouvez aussi utiliser la méthode ToXML() pour enregistrer les données dans un fichier XML :
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Vous pouvez afficher ces fichiers à l’aide de Windows Internet Explorer, Microsoft Visual Studio ou toute autre application capable d’ouvrir des fichiers HTML/XML.
  
Les transactions synthétiques exécutées à l’intérieur de System Center Operations Manager génèrent automatiquement ces fichiers journaux pour les échecs. Ces journaux ne seront pas générés si l’exécution échoue avant que Skype entreprise Server PowerShell ne puisse charger et exécuter la transaction synthétique. 
  
> [!IMPORTANT]
> Par défaut, Skype entreprise Server enregistre les fichiers journaux dans un dossier qui n’est pas partagé. Pour faciliter l’accès à ces journaux, vous devez partager ce dossier. Par exemple : \\ATL-Watcher-001. litwareinc. com\WatcherNode. 
