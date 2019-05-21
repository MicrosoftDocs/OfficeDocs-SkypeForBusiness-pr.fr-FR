---
title: Configuration de la messagerie unifiée d’Exchange Server pour la messagerie vocale de Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Résumé: configuration de la messagerie unifiée Exchange Server pour la messagerie vocale Skype entreprise Server.'
ms.openlocfilehash: a1c83b4ec92e6e3b3d678d2d7e0a65f58fc9d6ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278184"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Configuration de la messagerie unifiée d’Exchange Server pour la messagerie vocale de Skype Entreprise Server
 
**Résumé:** Configuration de la messagerie unifiée Exchange Server pour la messagerie vocale Skype entreprise Server.
  
Skype entreprise Server vous permet de disposer de messages vocaux stockés dans Exchange Server 2016 ou Exchange Server 2013. ces messages vocaux apparaissent alors sous forme de courriers dans les boîtes de réception de vos utilisateurs. 

> [!NOTE]
> La messagerie unifiée Exchange telle qu’auparavant connue n’est plus disponible dans Exchange 2019, mais vous pouvez toujours utiliser le système téléphonique pour enregistrer les messages vocaux, puis conserver l’enregistrement dans la boîte aux lettres Exchange d’un utilisateur. Pour plus d’informations, voir [planifier le service de messagerie vocale Cloud](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .
  
Si vous avez déjà configuré l’authentification de serveur à serveur entre Skype entreprise Server et Exchange Server 2016 ou Exchange Server 2013, vous pouvez configurer la messagerie unifiée. Pour ce faire, vous devez commencer par créer et affecter un nouveau plan de numérotation de messagerie unifiée sur votre serveur Exchange. Par exemple, ces deux commandes (exécutées à partir d’Exchange Management Shell) configurent un nouveau plan de numérotation à 3 chiffres pour Exchange:
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

Dans la première commande de l’exemple, le paramètre VoIPSecurity et la valeur de paramètre «Secured» indiquent que le canal de signalisation est chiffré à l’aide de TLS (Transport Layer Security). La valeur « SipName » de URIType indique que les messages seront envoyés et reçus à l’aide du protocole SIP et la valeur 1 de CountryOrRegionCode signifie que le plan de numérotation s’applique aux États-Unis.
  
Dans la seconde commande, la valeur transmise au paramètre ConfiguredInCountryOrRegionGroups indique quels groupes régionaux peuvent être utilisés avec ce plan de numérotation. La valeur de paramètre «Anywhere\*,\*,\*» définit les éléments suivants:
  
- Nom du groupe (« Anywhere »)
    
- AllowedNumberString (\*un caractère générique indiquant qu’une chaîne numérique est autorisée)
    
- DialNumberString (\*un caractère générique indiquant qu’un numéro composé est autorisé)
    
- TextComment (\*un caractère générique indiquant qu’une commande de texte est autorisée)
    
> [!NOTE]
> Quand vous créez un nouveau plan de numérotation, vous créez aussi une stratégie de boîte aux lettres par défaut. 
  
Après avoir créé et configuré le nouveau plan de numérotation, vous devez ajouter le nouveau plan de numérotation à votre serveur de messagerie unifiée, puis modifier le mode de démarrage de ce serveur. en particulier, vous devez définir le mode de démarrage sur «Dual». Vous pouvez effectuer les deux tâches suivantes à partir d’Exchange Management Shell:
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Après avoir configuré le serveur de messagerie unifiée, vous devez exécuter l’applet de certification Enable-ExchangeCertificate pour vous assurer que votre certificat Exchange est appliqué au service de messagerie unifiée:
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

Une fois le certificat correctement affecté, vous devez arrêter et redémarrer le service MsExchangeUM sur le serveur de messagerie unifiée. Ce service doit être arrêté et redémarré à chaque fois que vous modifiez le mode de démarrage.
  
Une fois la configuration du serveur de messagerie unifiée terminée, vous pouvez passer à la configuration du routeur d’appels de la messagerie unifiée :
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Comme le mode de démarrage a été modifié, vous devez arrêter et redémarrer le service MsExchangeUMCR sur l’ordinateur qui héberge le routeur d’appels de la messagerie unifiée.
  
Pour terminer la configuration de la messagerie unifiée, vous devez ensuite créer une stratégie de boîte aux lettres de la messagerie unifiée et utiliser cette stratégie afin d’activer les utilisateurs pour la messagerie unifiée. Vous pouvez créer une stratégie de boîte aux lettres à l’aide d’une commande similaire à celle-ci :
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

Vous pouvez également activer un utilisateur pour la messagerie unifiée en utilisant une commande semblable à celle-ci :
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

Dans la commande précédente, le paramètre Extensions représente le numéro de poste de l’utilisateur. Dans cet exemple, le numéro de poste de l’utilisateur est le 100.
  
Une fois sa boîte aux lettres activée, l’utilisateur kenmyer@litwareinc.com doit être en mesure d’utiliser la messagerie unifiée Exchange. Vous pouvez vérifier que l’utilisateur peut se connecter à la messagerie unifiée Exchange en exécutant l’applet de [contrôle test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) à partir de Skype entreprise Server Management Shell:
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Si un second utilisateur a été activé pour la messagerie unifiée, vous pouvez utiliser l’applet de commande [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) pour vous assurer qu’il est en mesure de laisser un message vocal au premier utilisateur.
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Configuration de la messagerie unifiée sur Microsoft Exchange Server 
> [!IMPORTANT]
> Si vous souhaitez utiliser la messagerie unifiée Exchange pour fournir des réponses aux appels, à Outlook Voice Access ou à des services de standard automatique pour les utilisateurs voix entreprise, voir [plan pour l’intégration de la messagerie unifiée Exchange dans Skype entreprise](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), puis suivez les instructions de cette section. 

Pour configurer la messagerie unifiée (MU) Exchange pour qu’elle fonctionne avec la voix entreprise, vous devez effectuer les tâches suivantes:

- Configurer des certificats sur le serveur exécutant les services de messagerie unifiée Exchange
  > [!NOTE]
  > Ajoutez tous les serveurs d’accès client et de boîte aux lettres à toutes les offres de numérotation URI SIP UM. Si ce n’est pas le cas, le routage des appels sortants ne fonctionne pas comme prévu. 
- Créez un ou plusieurs plans de numérotation URI SIP UM, ainsi que les numéros de téléphone d’accès d’abonné, le cas échéant, puis créez les plans de numérotation correspondants.

- Utilisez le script exchucutil. ps1 pour effectuer les opérations suivantes:
    - Créer des passerelles IP de messagerie unifiée.
    - Créer des groupes de recherche de MU.
    - Accordez l’autorisation de Skype entreprise Server pour lire les objets des services de domaine Active Directory UM.
- Créer un objet de standard automatique de messagerie unifiée.
- Créer un objet d’accès abonné.
- Créer un URI SIP pour chaque utilisateur et en associant les utilisateurs à l’aide d’un plan de numérotation URI SIP UM.

### <a name="requirements-and-recommendations"></a>Conditions requises et recommandations

Avant de commencer, la documentation de cette section part du principe que vous avez déployé les rôles Exchange suivants: accès client et boîte aux lettres. Dans Microsoft Exchange Server, la messagerie unifiée Exchange s’exécute en tant que service sur ces serveurs.

Notez également ce qui suit:
- Si Exchange UM est installé dans plusieurs forêts, vous devez effectuer les étapes d’intégration d’Exchange Server pour chaque forêt de messagerie unifiée. De plus, chaque forêt de messagerie unifiée doit être configurée pour approuver la forêt dans laquelle Skype entreprise Server est déployée et la forêt dans whichSkype pour Business Server est déployée de manière à approuver chaque forêt UM.
- Des étapes d’intégration sont effectuées à la fois sur les rôles de serveur Exchange et sur le serveur exécutant Skype entreprise Server. Vous devez effectuer les étapes d’intégration de la messagerie unifiée Exchange Server avant d’effectuer les étapes d’intégration de Lync Server 2013.
  > [!NOTE]
  > Pour savoir quelles étapes d’intégration sont exécutées sur les serveurs et quels rôles d’administrateur, voir [vue d’ensemble du processus de déploiement pour l’intégration de la messagerie unifiée locale et de Skype entreprise](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

Les outils suivants doivent être disponibles sur chaque serveur exécutant la messagerie unifiée Exchange:
- Exchange Management Shell
- Le script exchucutil. ps1, qui effectue les tâches suivantes:
    - Crée une passerelle IP de MU pour chaque serveur Skype entreprise.
    - Crée un groupe de recherche pour chaque passerelle. L’identificateur pilote de chaque groupe de recherche spécifie le plan de numérotation d’URI SIP de MU utilisé par le pool frontal ou le serveur Standard Edition associé à la passerelle.
    - Octroie à Skype entreprise Server une autorisation de lecture d’objets UM Exchange dans les services de domaine Active Directory (AD FS).



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1 

Lorsque vous intégrez Microsoft Skype entreprise Server à la messagerie unifiée Exchange (MU), vous devez exécuter le script ExchUcUtil. ps1 dans l’interpréteur de messages. Le script ExchUcUtil. ps1 effectue les opérations suivantes:

- Crée une passerelle IP de messagerie unifiée pour chaque pool Skype entreprise Server.

> [!IMPORTANT]
> Le script ExchUcUtil. ps1 crée une ou plusieurs passerelles IP de messagerie unifiée. Vous devez désactiver les appels sortants sur toutes les passerelles IP de messagerie unifiée, à l’exception d’une passerelle créée par le script. Cela inclut la désactivation des appels sortants sur les passerelles IP de MU qui ont été créées avant d’exécuter le script. 

- Crée un groupe de recherche de MU pour chaque passerelle IP de messagerie unifiée. L’identificateur pilote de chaque groupe de recherche spécifie le plan de numérotation d’URI SIP de MU utilisé par le pool frontal de Skype entreprise Server ou le serveur Standard Edition associé à la passerelle IP de messagerie unifiée.
- Octroie à Skype entreprise Server l’autorisation de lire les objets du conteneur de MU Active Directory, tels que les plans de numérotation de messagerie unifiée, les standards automatiques, les passerelles IP de messagerie unifiée et les groupes de recherche de MU.
  > [!IMPORTANT]
  > Chaque forêt UM doit être configurée pour approuver la forêt dans laquelle Skype entreprise Server est déployée et la forêt de déploiement de Skype entreprise Server 2013 doit être configurée pour faire confiance à chaque forêt UM. Si Exchange UM est installé dans plusieurs forêts, vous devez effectuer les étapes d’intégration d’Exchange Server pour chaque forêt de messagerie unifiée ou spécifier le domaine Skype entreprise Server. Par exemple, ExchUcUtil. ps1 – forêt: <lync-Domain-Controller-fqdn>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Utiliser le Shell pour exécuter le script ExchUcUtil. ps1

Exécutez le script ExchUcUtil. ps1 sur tout serveur Exchange de votre organisation qui se trouve dans la même topologie que Skype entreprise Server. Vous pouvez exécuter le script à partir d’un serveur de boîte aux lettres à l’aide de l’interpréteur de commande ou vous pouvez exécuter le script à l’aide de Windows PowerShell distant sur un serveur d’accès client. Si vous exécutez le script sur un serveur d’accès client de votre organisation, le serveur d’accès au client va mettre en proxy la session Windows PowerShell distante vers un serveur de boîtes aux lettres de l’organisation.
> [!IMPORTANT]
> Le script ExchUcUtil. ps1 crée une ou plusieurs passerelles IP de messagerie unifiée. Vous devez désactiver les appels sortants sur toutes les passerelles IP de messagerie unifiée, à l’exception d’une passerelle créée par le script. Cela inclut la désactivation des appels sortants sur les passerelles IP de MU qui ont été créées avant d’exécuter le script. Pour désactiver les appels sortants sur une passerelle IP de messagerie unifiée, voir désactiver les appels sortants sur les passerelles de messagerie unifiée. 
> [!IMPORTANT]
> Vous devez disposer des autorisations du rôle gestion de l’organisation Exchange ou être membre du groupe de sécurité administrateurs d’organisation Exchange pour exécuter le script. 

1. Ouvrez Exchange Management Shell.
2. À l’invite C:\Windows\System32, tapez **CD \<Drive letter>: \Program Files\Microsoft\Exchange Server\V15\Scripts>. ExchUcUtil. ps1**, puis appuyez sur entrée.

#### <a name="how-do-you-know-this-worked"></a>Comment vérifier que l’opération a fonctionné?

Pour vérifier que le script ExchUcUtul. ps1 s’est terminé correctement, procédez comme suit:
- Utilisez l’applet de action Get-UMIPGateway ou le centre d’administration Exchange pour afficher les nouvelles passerelles IP de messagerie unifiée qui ont été créées.
- Utilisez l’applet de recherche Get-UMHuntGroup ou le centre d’administration Exchange pour afficher le ou les groupes de recherche de MU qui ont été créés.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Configurer des certificats sur le serveur exécutant la messagerie unifiée Exchange Server
 
Si vous avez déployé la messagerie unifiée Exchange, comme décrit dans la section planification de l’intégration de la messagerie unifiée Exchange dans Skype entreprise Server dans la documentation de planification, et si vous souhaitez fournir des fonctionnalités de messagerie unifiée Exchange aux utilisateurs d’Enterprise Voice dans votre dans l’organisation, vous pouvez utiliser les procédures suivantes pour configurer le certificat sur le serveur exécutant la messagerie unifiée Exchange.

> [!IMPORTANT]
> Pour les certificats internes, les serveurs exécutant Skype entreprise Server et les serveurs exécutant Microsoft Exchange doivent disposer de certificats d’autorité racine approuvés qui sont mutuellement approuvés. L’autorité de certification (CA) peut être le même, ou une autre autorité de certification, tant que le certificat racine de l’autorité de certification est inscrit sur les serveurs dans leur magasin de certificats. 

Pour que vous puissiez vous connecter à Skype entreprise Server, le serveur Exchange doit être configuré à l’aide d’un certificat de serveur:
1. Téléchargez le certificat d’autorité de certification du serveur Exchange.
2. Installez le certificat d’autorité de certification du serveur Exchange.
3. Vérifiez que la CA figure dans la liste des autorités de certification racines de confiance du serveur Exchange.
4. Créez une demande de certificat pour le serveur Exchange et installez le certificat. 
5. Attribuez le certificat du serveur Exchange.


**Pour télécharger le certificat d’autorité de certification:**

1. Sur le serveur exécutant la messagerie unifiée Exchange, cliquez sur **Démarrer**, sur **exécuter**, tapez **le nom\<http://de votre autorité de certification émettrice Server>/certsrv**, puis cliquez sur **OK**.
2. Sous sélectionner une tâche, cliquez sur **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une LRC**.
3. Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une LRC**, sélectionnez **méthode d’encodage pour baser 64**, puis cliquez sur**Télécharger le certificat d’autorité de certification**.
   > [!NOTE]
   > Vous pouvez également spécifier le codage DER (Distinguished Encoding Rules) à cette étape. Si vous sélectionnez DER Encoding, le type de fichier à l’étape suivante de cette procédure et à l’étape 10 de **pour installer le certificat d’autorité de certification** est. p7b plutôt que. cer. 
4. Dans la boîte de dialogue **téléchargement de fichier** , cliquez sur **Enregistrer**, puis enregistrez le fichier sur le disque dur sur le serveur. (Le fichier aura une extension de fichier. cer ou. p7b, selon le codage que vous avez sélectionné à l’étape précédente.)

**Pour installer le certificat d’autorité de certification:**

1. Sur le serveur exécutant Exchange UM, ouvrez Microsoft Management Console (MMC) en cliquant sur **Démarrer**, sur **exécuter**, en tapant **MMC** dans la zone Ouvrir, puis en cliquant sur **OK**.
2. Dans le menu **fichier** , cliquez sur **Ajouter/supprimer un composant logiciel enfichable**, puis cliquez sur **Ajouter**.
3. Dans la boîte de dialogue **Ajouter des composants logiciels enfichables autonomes** , cliquez sur **certificats**, puis cliquez sur **Ajouter**.
4. Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.
5. Dans la boîte de dialogue **Sélectionner un ordinateur** , vérifiez que la case à cocher **ordinateur local: (l’ordinateur sur lequel cette console s’exécute)** est activée, puis cliquez sur **Terminer**.
6. Cliquez sur **Fermer**, puis cliquez sur **OK**. 
7. Dans l’arborescence de la console, développez **certificats (ordinateur local)**, développez **autorités de certification racine de confiance**, puis cliquez sur **certificats**.
8. Cliquez avec le bouton droit sur **certificats**, puis cliquez sur **toutes les tâches**et sur **Importer**.
9. Cliquez sur **Suivant**. 
10. Cliquez sur **Parcourir** pour rechercher le fichier, puis cliquez sur **suivant**. (Le fichier aura une extension de fichier. cer ou. p7b, selon le codage que vous avez sélectionné à l’étape 3 de **pour télécharger le certificat d’autorité de certification**.
11. Cliquez sur **Placer tous les certificats** dans le magasin suivant.
12. Cliquez sur **Parcourir**, puis sélectionnez **autorités de certification racines de confiance**. 
13. Cliquez sur **suivant** pour vérifier les paramètres, puis cliquez sur **Terminer**. 


**Pour vérifier que la CA figure dans la liste des autorités de certification racines de confiance:**

1. Sur le serveur exécutant la messagerie unifiée Exchange, dans MMC, développez certificats (ordinateur local), développez autorités de certification racine de confiance, puis cliquez sur certificats.
2. Dans le volet Détails, vérifiez que votre AC figure dans la liste des autorités de certification approuvées.


