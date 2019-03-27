---
title: Configuration de la messagerie unifiée d’Exchange Server pour la messagerie vocale de Skype Entreprise Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/11/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Résumé : Configurez messagerie unifiée Exchange Server pour Skype pour la messagerie vocale Business Server.'
ms.openlocfilehash: 60f9398b7a35ad211ede22ee0e0e7f9689bbc8d7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887899"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Configuration de la messagerie unifiée d’Exchange Server pour la messagerie vocale de Skype Entreprise Server
 
**Résumé :** Configurer la messagerie unifiée Exchange Server pour Skype pour la messagerie vocale Business Server.
  
Skype pour Business Server vous permet d’avoir des messages vocaux stockées dans Exchange Server 2016 ou Exchange Server 2013 ; Ces messages de messagerie vocale seront affiche alors en tant que messages électroniques dans la boîte de réception de vos utilisateurs. 

> [!NOTE]
> La messagerie unifiée Exchange comme connu précédemment n’est plus disponible dans Exchange 2019, mais vous pouvez toujours utiliser le système téléphonique aux messages d’enregistrement de la messagerie vocale et laissez l’enregistrement dans la boîte aux lettres Exchange de l’utilisateur. Pour plus d’informations, voir [service de planification de la messagerie vocale dans le nuage](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .
  
Si vous avez déjà configuré l’authentification de serveur à serveur entre Skype pour Business Server et Exchange Server 2016 ou Exchange Server 2013, vous êtes prêt à configurer la messagerie unifiée. Pour ce faire, vous devez tout d’abord créer et affecter un plan de numérotation de messagerie unifiée nouveau sur votre serveur Exchange. Par exemple, les deux commandes suivantes (exécutées à partir d’Exchange Management Shell) configurer un nouveau plan de numérotation à 3 chiffres pour Exchange :
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

Dans la première commande dans l’exemple, le paramètre VoIPSecurity et la valeur du paramètre « Sécurisé » indique que le canal de signalisation est chiffré à l’aide de Transport Layer Security (TLS). La valeur « SipName » de URIType indique que les messages seront envoyés et reçus à l’aide du protocole SIP et la valeur 1 de CountryOrRegionCode signifie que le plan de numérotation s’applique aux États-Unis.
  
Dans la seconde commande, la valeur transmise au paramètre ConfiguredInCountryOrRegionGroups indique quels groupes régionaux peuvent être utilisés avec ce plan de numérotation. La valeur du paramètre « n’importe où,\*,\*,\*» définit les éléments suivants :
  
- Nom du groupe (« Anywhere »)
    
- AllowedNumberString (\*, caractère générique indiquant que n’importe quelle chaîne de numéros est autorisée)
    
- DialNumberString (\*, caractère générique indiquant que n’importe quel numéro composé est autorisé)
    
- TextComment (\*, caractère générique indiquant que n’importe quelle commande texte est autorisée)
    
> [!NOTE]
> Quand vous créez un nouveau plan de numérotation, vous créez aussi une stratégie de boîte aux lettres par défaut. 
  
Après la création et la configuration du nouveau plan de numérotation, vous devez ajouter le nouveau plan à votre serveur de messagerie unifiée de numérotation et ensuite modifie le mode de démarrage du serveur ; en particulier, vous devez définir le mode de démarrage à « Double ». Vous pouvez effectuer les deux de ces tâches à partir d’Exchange Management Shell :
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Une fois que le serveur de messagerie unifiée a été configuré, vous devez exécuter l’applet de commande Enable-ExchangeCertificate pour vous assurer que votre certificat Exchange est appliquée à un service de messagerie unifiée :
  
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
  
Une fois sa boîte aux lettres activée, l’utilisateur kenmyer@litwareinc.com doit être en mesure d’utiliser la messagerie unifiée Exchange. Vous pouvez vérifier que l’utilisateur peut se connecter à la messagerie unifiée Exchange en exécutant l’applet de commande [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) à partir de la Skype pour Business Server Management Shell :
  
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
> Si vous souhaitez utiliser la messagerie unifiée Exchange (MU) pour fournir la réponse aux appels, Outlook Voice Access ou les services de standard automatique pour les utilisateurs d’Enterprise Voice, consultez [planifier l’intégration de la messagerie unifiée Exchange dans Skype pour les entreprises](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)et suivez les instructions de cette section. 

Pour configurer Exchange messagerie unifiée (MU) pour travailler avec Enterprise Voice, vous devez effectuer les tâches suivantes :

- Configurer des certificats sur le serveur exécutant les services de messagerie unifiée Exchange (MU)
  > [!NOTE]
  > Ajoutez tous les accès au Client et les serveurs de boîtes aux lettres à tous les plans de numérotation de messagerie unifiée les URI SIP. Si, le routage des appels sortants ne fonctionne pas comme prévu. 
- Créez un ou plusieurs plans de numérotation de MU les URI SIP, ainsi que de l’abonné accéder aux numéros de téléphone, selon vos besoins, puis créer des plans de numérotation L correspondants.

- Utilisez le script exchucutil.ps1 pour :
    - Créer des passerelles IP de messagerie unifiée.
    - Créer des groupements de postes de messagerie unifiée.
    - Accordez Skype pour l’autorisation de lire les objets de messagerie unifiée Active Directory Domain Services Business Server.
- Créer un objet de standard automatique de messagerie unifiée.
- Créer un objet d’accès abonné.
- Créez un URI SIP pour chaque utilisateur et l’associer des utilisateurs avec un plan de numérotation de messagerie unifiée les URI SIP.

### <a name="requirements-and-recommendations"></a>Conditions requises et recommandations

Avant de commencer, la documentation de cette section suppose que vous avez déployé les rôles Exchange suivants : accès au Client et boîte aux lettres. Dans Microsoft Exchange Server, la messagerie unifiée Exchange s’exécute en tant que service sur ces serveurs.

Notez également les éléments suivants :
- Si la messagerie unifiée Exchange est installée dans plusieurs forêts, les étapes d’intégration Exchange Server doivent être effectuées pour chaque forêt de messagerie unifiée. En outre, chaque forêt de messagerie unifiée doit être configuré pour approuver la forêt dans laquelle Skype pour Business Server est déployé et la forêt dans whichSkype pour Business Server est déployé doit être configurée pour l’approbation de chaque forêt de messagerie unifiée.
- Étapes d’intégration sont effectuées sur les deux les rôles de serveur Exchange exécutant des services de messagerie unifiée et sur le serveur exécutant Skype pour Business Server. Vous devez effectuer les étapes d’intégration de messagerie unifiée Exchange Server avant d’effectuer les étapes d’intégration de Lync Server 2013.
  > [!NOTE]
  > Pour voir quelles étapes d’intégration sont effectuées sur quels serveurs et par quels rôles d’administrateur, voir [vue d’ensemble du processus de déploiement pour l’intégration de la messagerie unifiée et locaux Skype pour les entreprises](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

Les outils suivants doivent être disponibles sur chaque serveur exécutant la messagerie unifiée Exchange :
- Exchange Management Shell
- Le script exchucutil.ps1, qui effectue les tâches suivantes :
    - Crée une passerelle IP de messagerie unifiée pour chaque Skype pour Business Server.
    - Crée un groupement de postes pour chaque passerelle. L’identificateur pilote de chaque groupe de recherche spécifie le plan de numérotation de messagerie unifiée les URI SIP utilisé par le pool frontal ou un serveur Standard Edition server qui est associé à la passerelle.
    - Accorde Skype pour Business Server l’autorisation Lire les objets de messagerie unifiée Exchange dans les Services de domaine Active Directory.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1 

Lorsque vous êtes intégration Microsoft Skype pour Business Server avec Exchange messagerie unifiée (MU), vous devez exécuter le script ExchUcUtil.ps1 dans le Shell. Le script ExchUcUtil.ps1 effectue les opérations suivantes :

- Crée une passerelle IP de messagerie unifiée pour chaque Skype pour le pool de serveurs d’entreprise.

> [!IMPORTANT]
> Le script ExchUcUtil.ps1 crée une ou plusieurs passerelles IP de messagerie unifiée. Vous devez désactiver les appels sortants sur toutes les passerelles IP de messagerie unifiée à l’exception d’une passerelle que le script créé. Cela inclut la désactivation des appels sortants sur les passerelles IP de messagerie unifiée qui ont été créées avant d’exécuter le script. 

- Crée un groupement de postes de messagerie unifiée pour chaque passerelle IP de messagerie unifiée. L’identificateur pilote de chaque groupe de recherche spécifie le plan de numérotation de messagerie unifiée les URI SIP utilisé par le Skype pour Business Server frontal ou serveur Standard Edition server qui est associé à la passerelle IP de messagerie unifiée.
- Accorde Skype pour Business Server l’autorisation de lecture de numérotation de messagerie unifiée Active Directory des objets conteneurs tels que la messagerie unifiée plans, les standards automatiques, les passerelles IP de messagerie unifiée et groupements de postes de messagerie unifiée.
  > [!IMPORTANT]
  > Chacune des forêts doivent être configuré pour approuver la forêt dans laquelle Skype pour Business Server est déployé et la forêt dans laquelle est déployé Skype pour Business Server 2013 doit être configurée pour l’approbation de chaque forêt de messagerie unifiée. Si la messagerie unifiée Exchange est installée dans plusieurs forêts, les étapes d’intégration Exchange Server doivent être effectuées pour chaque forêt de messagerie unifiée ou vous devrez spécifier le Skype pour le domaine du serveur d’entreprise. Par exemple, ExchUcUtil.ps1 – forêt : <lync-domaine-contrôleur-fqdn>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Utiliser le Shell pour exécuter le script ExchUcUtil.ps1

Exécutez le script ExchUcUtil.ps1 sur n’importe quel serveur Exchange dans votre organisation qui se trouve dans la même topologie que Skype pour Business Server. Vous pouvez exécuter le script à partir d’un serveur de boîtes aux lettres à l’aide de l’interpréteur de commandes ou vous pouvez exécuter le script à l’aide de Windows PowerShell à distance sur un serveur d’accès au Client. Si vous exécutez le script sur un serveur d’accès au Client dans votre organisation, le serveur d’accès Client sera proxy la session Windows PowerShell à distance sur un serveur de boîtes aux lettres dans l’organisation.
> [!IMPORTANT]
> Le script ExchUcUtil.ps1 crée une ou plusieurs passerelles IP de messagerie unifiée. Vous devez désactiver les appels sortants sur toutes les passerelles IP de messagerie unifiée à l’exception d’une passerelle que le script créé. Cela inclut la désactivation des appels sortants sur les passerelles IP de messagerie unifiée qui ont été créées avant d’exécuter le script. Pour désactiver les appels sortants sur une passerelle IP de messagerie unifiée, voir Disable sortant des appels sur les passerelles IP de messagerie unifiée. 
> [!IMPORTANT]
> Vous devez disposer des autorisations du rôle de gestion de l’organisation Exchange ou être membre du groupe de sécurité administrateurs de l’organisation Exchange pour exécuter le script. 

1. Ouvrez Exchange Management Shell.
2. À l’invite C:\Windows\System32, tapez cd ** \<letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts> du lecteur. ExchUcUtil.ps1**, puis appuyez sur ENTRÉE.

#### <a name="how-do-you-know-this-worked"></a>Comment savoir si cela a fonctionné ?

Pour vérifier que le script exchucutul.ps1 a été exécuté correctement effectuée, procédez comme suit :
- Utilisez l’applet de commande Get-UMIPGateway ou le CAE pour afficher la nouvelle passerelle IP de messagerie unifiée ou des passerelles qui ont été créées.
- Utilisez l’applet de commande Get-UMHuntGroup ou le CAE pour afficher le nouveau groupement de postes de messagerie unifiée ou des groupes qui ont été créées.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Configurer des certificats sur le serveur exécutant la messagerie unifiée Exchange Server
 
Si vous avez déployé Exchange messagerie unifiée (MU), comme décrit dans la planification de l’intégration de la messagerie unifiée Exchange dans Skype pour Business Server dans la documentation de planification et que vous souhaitez fournir des fonctionnalités de messagerie unifiée Exchange aux utilisateurs d’Enterprise Voice dans votre organisation, vous pouvez utiliser les procédures suivantes pour configurer le certificat sur le serveur exécutant la messagerie unifiée Exchange.

> [!IMPORTANT]
> Pour les certificats internes, les serveurs exécutant Skype pour Business Server et les serveurs exécutant Microsoft Exchange doivent avoir approuvé certificats autorité racine approuvées. L’autorité de certification (CA) peut être les mêmes, ou une autorité de certification différente, dans la mesure où les serveurs ont le certificat racine de l’autorité de certification inscrit dans leur magasin de certificats d’autorité racine de confiance. 

Le serveur Exchange doit être configuré avec un certificat de serveur afin de se connecter à Skype pour Business Server :
1. Télécharger le certificat d’autorité de certification pour le serveur Exchange.
2. Installer le certificat d’autorité de certification pour le serveur Exchange.
3. Vérifiez que l’autorité de certification figure dans la liste des autorités de certification du serveur Exchange racine.
4. Créer une demande de certificat pour le serveur Exchange et installer le certificat. 
5. Assignez le certificat pour le serveur Exchange.


**Pour télécharger le certificat d’autorité de certification :**

1. Sur le serveur exécutant la messagerie unifiée Exchange, cliquez sur **Démarrer**, sur **exécuter**, type **http://\<nom de votre autorité de certification émettrice Server>/certsrv**, puis cliquez sur **OK**.
2. Sous Sélectionnez une tâche, cliquez sur **télécharger un certificat autorité de certification, chaîne de certificats ou une liste de révocation**.
3. Sous **télécharger un certificat d’autorité de certification, la chaîne de certificats ou la révocation de certificats**, sélectionnez la **Méthode de codage Base 64**, puis cliquez sur**Télécharger l’autorité de certification**.
   > [!NOTE]
   > Vous pouvez également spécifier de codage unique codage DER (Rules). Si vous sélectionnez cette méthode, le type de fichier à l’étape suivante de cette procédure et à l’étape 10 **pour installer l’autorité de certification le certificat** est .p7b et non .cer. 
4. Dans la boîte de dialogue **Téléchargement de fichier** , cliquez sur **Enregistrer**, puis enregistrez le fichier sur le disque dur sur le serveur. (Le fichier aura .cer ou une extension de fichier .p7b, selon la méthode de codage que vous avez sélectionné à l’étape précédente.)

**Pour installer le certificat d’autorité de certification :**

1. Sur le serveur exécutant la messagerie unifiée Exchange, ouvrez Microsoft Management Console (MMC) en cliquant sur **Démarrer**, sur **exécuter**, en tapant **mmc** dans la zone Ouvrir, puis en cliquant sur **OK**.
2. Dans le menu **fichier** , cliquez sur **Ajouter/supprimer un composant logiciel enfichable**, puis cliquez sur **Ajouter**.
3. Dans la zone **Ajouter enfichables** , cliquez sur **certificats**, puis cliquez sur **Ajouter**.
4. Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.
5. Dans la boîte de dialogue **Sélectionner un ordinateur** , vérifiez que le **ordinateur Local : (l’ordinateur cette console s’exécute)** case à cocher est activée, puis cliquez sur **Terminer**.
6. Cliquez sur **Fermer**, puis cliquez sur **OK**. 
7. Dans l’arborescence de la console, développez **certificats (ordinateur Local)**, développez **Autorités de Certification racines de confiance**, puis cliquez sur **certificats**.
8. Avec le bouton droit de **certificats**et cliquez sur **Toutes les tâches**, cliquez sur **Importer**.
9. Cliquez sur **Suivant**. 
10. Cliquez sur **Parcourir** pour localiser le fichier, puis cliquez sur **suivant**. (Le fichier aura .cer ou une extension de fichier .p7b, selon la méthode de codage que vous avez sélectionné à l’étape 3 de **pour télécharger le certificat d’autorité de certification**.
11. Cliquez sur **Placer tous les certificats** dans le magasin suivant.
12. Cliquez sur **Parcourir**, puis sélectionnez **Autorités de Certification racines de confiance**. 
13. Cliquez sur **suivant** pour vérifier les paramètres, puis cliquez sur **Terminer**. 


**Pour vérifier que l’autorité de certification figure dans la liste des autorités de certification racines :**

1. Sur le serveur exécutant la messagerie unifiée Exchange, dans la console MMC, développez Certificats (ordinateur Local), développez Autorités de Certification racines de confiance, puis sur certificats.
2. Dans le volet détails, vérifiez que votre autorité de certification figure dans la liste des autorités de certification approuvées.


