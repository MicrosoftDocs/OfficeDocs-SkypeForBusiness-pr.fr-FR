---
title: Configurer Exchange Server messagerie unifiée pour Skype Entreprise Server messagerie vocale
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Résumé : Configurez Exchange Server messagerie unifiée pour Skype Entreprise Server messagerie vocale.'
ms.openlocfilehash: e434309c67469ccaa6994ec90cb3431b9de4f13b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865281"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Configurer Exchange Server messagerie unifiée pour Skype Entreprise Server messagerie vocale
 
**Résumé :** Configurez Exchange Server messagerie unifiée pour Skype Entreprise Server messagerie vocale.
  
Skype Entreprise Server vous permet de stocker des messages vocaux dans Exchange Server 2016 ou Exchange Server 2013 ; Ces messages vocaux s’affichent ensuite sous la plupart des messages électroniques dans la boîte de réception de vos utilisateurs. 

> [!NOTE]
> Exchange La messagerie unifiée comme précédemment connue n’est plus disponible dans Exchange 2019, mais vous pouvez toujours utiliser Système téléphonique pour enregistrer les messages vocaux, puis laisser l’enregistrement dans la boîte aux lettres Exchange d’un utilisateur. Pour [plus d’informations, voir Messagerie vocale infonuagique service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) de plan.
  
Si vous avez déjà configuré l’authentification de serveur à serveur entre Skype Entreprise Server et Exchange Server 2016 ou Exchange Server 2013, vous êtes prêt à configurer la messagerie unifiée. Pour ce faire, vous devez d’abord créer et affecter un nouveau plan de numérotation de messagerie unifiée sur votre Exchange Server. Par exemple, ces deux commandes (exécutés à partir de Exchange Management Shell) configurent un nouveau plan de numérotation à 3 chiffres pour Exchange :
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

Dans la première commande de l’exemple, le paramètre VoIPSecurity et la valeur de paramètre « Secured » indiquent que le canal de signalisation est chiffré à l’aide de TLS (Transport Layer Security). La valeur « SipName » de URIType indique que les messages seront envoyés et reçus à l’aide du protocole SIP et la valeur 1 de CountryOrRegionCode signifie que le plan de numérotation s’applique aux États-Unis.
  
Dans la seconde commande, la valeur transmise au paramètre ConfiguredInCountryOrRegionGroups indique quels groupes régionaux peuvent être utilisés avec ce plan de numérotation. La valeur de paramètre « Anywhere, \* , », définit les \* \* valeurs suivantes :
  
- Nom du groupe (« Anywhere »)
    
- AllowedNumberString ( \* , caractère générique indiquant que n’importe quelle chaîne de nombre est autorisée)
    
- DialNumberString ( , caractère générique indiquant que n’importe quel \* numéro composé est autorisé)
    
- TextComment ( \* , caractère générique indiquant que n’importe quelle commande de texte est autorisée)
    
> [!NOTE]
> La création d’un nouveau plan de numérotation crée également une stratégie de boîte aux lettres par défaut. 
  
Après avoir créé et configuré le nouveau plan de numérotation, vous devez ajouter le nouveau plan de numérotation à votre serveur de messagerie unifiée, puis modifier le mode de démarrage de ce serveur . en particulier, vous devez définir le mode de démarrage sur « Double ». Vous pouvez effectuer ces deux tâches à partir de l’Exchange Management Shell :
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Une fois le serveur de messagerie unifiée configuré, vous devez exécuter la cmdlet Enable-ExchangeCertificate pour vous assurer que votre certificat Exchange est appliqué au service de messagerie unifiée :
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

Une fois le certificat correctement affecté, vous devez arrêter et redémarrer le service MsExchangeUM sur le serveur de messagerie unifiée. Ce service doit être arrêté et redémarré à chaque fois que vous modifiez le mode de démarrage.
  
Une fois la configuration du serveur de messagerie unifiée terminée, vous pouvez passer à la configuration du routeur d’appels de la messagerie unifiée :
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Comme le mode de démarrage a été modifié, vous devez arrêter et redémarrer le service MsExchangeUMCR sur l’ordinateur qui héberge le routeur d’appels de la messagerie unifiée.
  
Pour terminer la configuration de la messagerie unifiée, vous devez ensuite créer une stratégie de boîte aux lettres de la messagerie unifiée et utiliser cette stratégie afin d’activer les utilisateurs pour la messagerie unifiée. Vous pouvez créer une stratégie de boîte aux lettres à l’aide d’une commande similaire à celle-ci :
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

Et vous pouvez activer un utilisateur pour la messagerie unifiée en utilisant une commande semblable à celle-ci :
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

Dans la commande précédente, le paramètre Extensions représente le numéro de poste de l’utilisateur. Dans cet exemple, le numéro de poste de l’utilisateur est le 100.
  
Une fois sa boîte aux lettres activée, l’utilisateur kenmyer@litwareinc.com doit être en mesure d’utiliser la messagerie unifiée Exchange. Vous pouvez vérifier que l’utilisateur peut se connecter à Exchange um en exécutant l’cmdlet [Test-CsExUMConnectivity](/powershell/module/skype/test-csexumconnectivity) à partir de Skype Entreprise Server Management Shell :
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Si un second utilisateur a été activé pour la messagerie unifiée, vous pouvez utiliser l’applet de commande [Test-CsExUMVoiceMail](/powershell/module/skype/test-csexumvoicemail) pour vous assurer qu’il est en mesure de laisser un message vocal au premier utilisateur.
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Configuration de la messagerie unifiée sur Microsoft Exchange Server 
> [!IMPORTANT]
> Si vous souhaitez utiliser la messagerie unifiée Exchange pour fournir des services de répondeurs automatiques, d’Outlook Voice Access ou de service de attendant automatique pour les utilisateurs de Voix Entreprise, lisez Planifier l’intégration de la messagerie unifiée Exchange dans [Skype Entreprise,](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)puis suivez les instructions de cette section. 

Pour configurer Exchange messagerie unifiée pour qu’elle fonctionne Voix Entreprise, vous devez effectuer les tâches suivantes :

- Configurer des certificats sur le serveur exécutant Exchange services de messagerie unifiée
  > [!NOTE]
  > Ajoutez tous les serveurs d’accès au client et de boîtes aux lettres à tous les plans de numérotation URI SIP de messagerie ungée. Si ce n’est pas le cas, le routage des appels sortants ne fonctionne pas comme prévu. 
- Créez un ou plusieurs plans de numérotation URI SIP de la um, ainsi que les numéros de téléphone d’accès d’abonné, selon vos besoins, puis créez les plans de numérotation L correspondants.

- Utilisez le script exchucutil.ps1 pour :
    - créer des passerelles IP de messagerie unifiée ;
    - créer des groupements de postes de messagerie unifiée ;
    - Accordez Skype Entreprise Server autorisation de lecture des objets des services de domaine Active Directory de la um.
- Créez un objet de attendant automatique de la um.
- Créez un objet d’accès abonné.
- Créez un URI SIP pour chaque utilisateur et associez des utilisateurs à un plan de numérotation URI SIP de la um.

### <a name="requirements-and-recommendations"></a>Conditions requises et recommandations

Avant de commencer, la documentation de cette section suppose que vous avez déployé les rôles Exchange suivants : accès au client et boîte aux lettres. Dans Microsoft Exchange Server, Exchange messagerie un jour s’exécute en tant que service sur ces serveurs.

Notez également les points suivants :
- Si Exchange de l’utilisateur est installée dans plusieurs forêts, les étapes Exchange Server’intégration doivent être effectuées pour chaque forêt de la um. En outre, chaque forêt de messagerie unie doit être configurée pour faire confiance à la forêt dans laquelle Skype Entreprise Server est déployé, et la forêt dans laquelleSkype for Business Server est déployé doit être configurée pour faire confiance à chaque forêt de messagerie unie.
- Les étapes d’intégration sont effectuées sur les rôles Exchange Server où les services de messagerie unifiée sont en cours d’exécution et sur le serveur exécutant Skype Entreprise Server. Vous devez effectuer les étapes Exchange Server’intégration de la messagerie unifiée avant d’effectuer les étapes d’intégration de Lync Server 2013.
  > [!NOTE]
  > Pour voir [quelles étapes](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)d’intégration sont effectuées sur quels serveurs et par quels rôles d’administrateur, voir Vue d’ensemble du processus de déploiement pour l’intégration de la messagerie unifiée et des Skype Entreprise . 

Les outils suivants doivent être disponibles sur chaque serveur exécutant une messagerie Exchange messagerie un peu plus courante :
- Environnement de ligne de commande Exchange Management Shell
- Le script exchucutil.ps1, exécute les tâches suivantes :
    - Crée une passerelle IP de um pour chaque Skype Entreprise Server.
    - Il crée un groupement de postes pour chaque passerelle. L’identificateur pilote de chaque groupement de recherche spécifie le plan de numérotation URI SIP de messagerie ungée utilisé par le pool frontal ou le serveur Édition Standard associé à la passerelle.
    - Accorde Skype Entreprise Server l’autorisation de Exchange des objets de la Exchange dans les services de domaine Active Directory.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configurer la messagerie unifiée sur Microsoft Exchange avec ExchUCUtil.ps1 

Lorsque vous intégrez Microsoft Skype Entreprise Server à Exchange messagerie unifiée, vous devez exécuter le script ExchUcUtil.ps1 dans l’shell. Le script ExchUcUtil.ps1 effectue les opérations suivantes :

- Crée une passerelle IP de um pour chaque pool Skype Entreprise Server de données.

> [!IMPORTANT]
> Le script ExchUcUtil.ps1 crée une ou plusieurs passerelles IP de messagerie unifiée. Vous devez désactiver les appels sortants sur toutes les passerelles IP de messagerie unifiée à l'exception de celle que le script a créée. Ceci inclut la désactivation des appels sortants sur les passerelles IP de messagerie unifiée qui ont été créées avant l'exécution du script. 

- Il crée un groupement de postes de messagerie unifiée pour chaque passerelle IP de messagerie unifiée. L’identificateur pilote de chaque groupement de recherche spécifie le plan de numérotation URI SIP de messagerie ungée utilisé par le pool frontal Skype Entreprise Server ou le serveur Édition Standard associé à la passerelle IP de messagerie ungée.
- Accorde Skype Entreprise Server l’autorisation de lire les objets conteneur de la um Active Directory tels que les plans de numérotation de la um, les attendants automatiques, les passerelles IP de um et les groupements de recherche de um.
  > [!IMPORTANT]
  > Chaque forêt de la um doit être configurée pour faire confiance à la forêt dans laquelle Skype Entreprise Server est déployé, et la forêt dans laquelle Skype Entreprise Server 2013 est déployé doit être configurée pour faire confiance à chaque forêt de um. Si la Exchange est installée dans plusieurs forêts, les étapes d’intégration Exchange Server doivent être effectuées pour chaque forêt de la Skype Entreprise Server de la Skype Entreprise Server. Par exemple, ExchUcUtil.ps1 –Forest: \<lync-domain-controller-fqdn> . 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Utiliser l’environnement Shell pour exécuter le script ExchUcUtil.ps1

Exécutez le script ExchUcUtil.ps1 sur n’importe quel serveur Exchange de votre organisation qui se trouverait dans la même topologie que Skype Entreprise Server. Vous pouvez exécuter le script à partir d'un serveur de boîtes aux lettres en utilisant l'environnement Shell ou vous pouvez l'exécuter à l'aide de Remote Windows PowerShell sur un serveur d'accès au client. Si vous exécutez le script sur un serveur d'accès au client de votre organisation, le serveur d'accès au client redirigera via proxy la session Remote Windows PowerShell vers un serveur de boîtes aux lettres dans l'organisation.
> [!IMPORTANT]
> Le script ExchUcUtil.ps1 crée une ou plusieurs passerelles IP de messagerie unifiée. Vous devez désactiver les appels sortants sur toutes les passerelles IP de messagerie unifiée à l'exception de celle que le script a créée. Ceci inclut la désactivation des appels sortants sur les passerelles IP de messagerie unifiée qui ont été créées avant l'exécution du script. Pour désactiver les appels sortants sur une passerelle IP de messagerie unifiée, consultez la rubrique Désactiver les appels sortants sur les passerelles IP de messagerie unifiée.[!IMPORTANT]
> Vous devez avoir les autorisations du rôle Gestion de l'organisation Exchange ou être membre du groupe de sécurité Administrateurs d'organisation Exchange pour exécuter le script. 

1. Ouvrez l'environnement de ligne de commande Exchange Management Shell.
2. À l’invite C:\Windows\System32, tapez **cd \<drive letter> :\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1,** puis appuyez sur Entrée.

#### <a name="how-do-you-know-this-worked"></a>Comment savoir si cela a fonctionné ?

Pour vérifier que le script ExchUcUtul.ps1 a été exécuté correctement, procédez comme suit :
- Utilisez la cmdlet Get-UMIPGateway ou le CAE pour voir la nouvelle passerelle IP de messagerie unifiée ou des passerelles qui ont été créées.
- Utilisez la cmdlet Get-UMHuntGroup ou le CAE pour voir le nouveau groupement de postes de messagerie unifiée ou des groupes qui ont été créés.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Configurer des certificats sur le serveur exécutant Exchange Server messagerie unifiée
 
Si vous avez déployé la messagerie unifiée Exchange, comme décrit dans la planification de l’intégration de la messagerie unifiée Exchange dans Skype Entreprise Server dans la documentation de planification et que vous souhaitez fournir des fonctionnalités de messagerie unifiée Exchange aux Voix Entreprise utilisateurs de votre organisation, vous pouvez utilisez les procédures suivantes pour configurer le certificat sur le serveur exécutant Exchange messagerie unie.

> [!IMPORTANT]
> Pour les certificats internes, les serveurs exécutant Skype Entreprise Server et les serveurs exécutant Microsoft Exchange doivent avoir des certificats d’autorité racines de confiance mutuellement fiables. L’autorité de certification peut être la même ou une autorité de certification différente, tant que le certificat racine de l’autorité de certification est inscrit dans le magasin de certificats de l’autorité racine de confiance des serveurs. 

Le Exchange Server doit être configuré avec un certificat de serveur pour se connecter à Skype Entreprise Server :
1. Téléchargez le certificat d’autorité de certification du serveur Exchange Server.
2. Installez le certificat d’autorité de certification du serveur Exchange Server.
3. Vérifiez que l’autorité de certification figure dans la liste des autorités de certification racines de confiance du serveur Exchange Server.
4. Créez une demande de certificat pour le serveur Exchange Server et installez le certificat. 
5. Assignez le certificat du serveur Exchange Server.


**Pour télécharger le certificat de l’ac :**

1. Sur le serveur exécutant Exchange messagerie un Exchange, cliquez sur **Démarrer,** cliquez sur **Exécuter,** tapez **http:// \<name of your Issuing CA Server> /certsrv,** puis cliquez sur **OK**.
2. Sous Sélectionner une tâche, cliquez **sur Télécharger un certificat d’ac, une chaîne de certificats ou une CRL.**
3. Sous **Télécharger un certificat d’ac,** une chaîne de certificats ou une CRL, sélectionnez La méthode de codage en **base 64,** puis cliquez sur Télécharger le certificat de l’ac.
   > [!NOTE]
   > Vous pouvez également spécifier Distinguished Encoding Rules codage (DER) à cette étape. Si vous sélectionnez cette méthode, le fichier spécifié à l’étape suivante de cette procédure et à l’étape 10 de la procédure **Pour installer le certificat de l’autorité de certification** sera de type .p7b et non .cer. 
4. Dans la boîte de dialogue **Téléchargement de fichier**, cliquez sur **Enregistrer**, puis enregistrez le fichier sur le disque dur du serveur (le fichier sera doté de l’extension .cer ou .p7b, selon la méthode de codage que vous avez sélectionnée à l’étape précédente).

**Pour installer le certificat d’ac :**

1. Sur le serveur exécutant la messagerie un Exchange, ouvrez la console MMC (Microsoft Management Console) en cliquant sur **Démarrer,** sur **Exécuter,** en tapant **mmc** dans la zone Ouvrir, puis en cliquant sur **OK.**
2. Dans le menu **Fichier**, cliquez sur **Ajouter/Supprimer un composant logiciel enfichable**, puis sur **Ajouter**.
3. Dans la zone **Ajout d’un composant logiciel enfichable autonome**, cliquez sur **Certificats**, puis sur **Ajouter**.
4. Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.
5. Dans la **boîte de** dialogue Sélectionner un ordinateur, vérifiez que la case à cocher Ordinateur local : (l’ordinateur sur qui cette console est en cours d’exécution) est cocher, puis cliquez sur **Terminer**. 
6. Cliquez sur **Fermer**, puis sur **OK**. 
7. Dans l’arborescence de la console, développez **Certificats (ordinateur local)**, développez **Autorités de certification racines de confiance**, puis cliquez sur **Certificats**.
8. Cliquez avec le bouton droit sur **Certificats**, cliquez sur **Toutes les tâches**, puis sur **Importer**.
9. Cliquez sur **Suivant**. 
10. Cliquez sur **Parcourir** pour localiser le fichier, puis cliquez sur **Suivant**. Le fichier sera doté de l’extension .cer ou .p7b, selon la méthode de codage sélectionnée à l’étape 3 de la procédure **Pour télécharger le certificat de l’autorité de certification**.
11. Cliquez **sur Placer tous les certificats** dans le magasin suivant.
12. Cliquez sur **Parcourir**, puis sélectionnez **Autorités de certification racines de confiance**. 
13. Cliquez sur **Suivant** pour vérifier les paramètres, puis sur **Terminer**. 


**Pour vérifier que l’ac figure dans la liste des ca racines de confiance :**

1. Sur le serveur exécutant la messagerie Exchange, dans la MMC, développez Certificats (ordinateur local), développez Autorités de certification racines de confiance, puis cliquez sur Certificats.
2. Dans le volet de détail, vérifiez que votre autorité de certification figure sur la liste des autorités de certification de confiance.