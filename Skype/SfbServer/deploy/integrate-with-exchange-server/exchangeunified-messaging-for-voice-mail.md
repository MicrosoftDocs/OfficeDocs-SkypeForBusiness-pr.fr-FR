---
title: Configuration de la messagerie unifiée d’Exchange Server pour la messagerie vocale de Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/19/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Résumé : Configuration messagerie unifiée d’Exchange Server pour Skype pour la messagerie vocale Business Server.'
ms.openlocfilehash: 9f4cb3dcd43d8f6300a5fbe38bd37c40d48e8273
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a>Configuration de la messagerie unifiée d’Exchange Server pour la messagerie vocale de Skype Entreprise Server 2015
 
**Résumé :** Configurer la messagerie unifiée Exchange Server pour Skype pour la messagerie vocale Business Server.
  
Skype pour Business Server 2015 vous permet d’avoir des messages vocaux stockées dans Exchange Server 2016 ou 2013 d’Exchange Server ; les messages de la messagerie vocale seront affiche alors en tant que messages électroniques dans les boîtes de réception de vos utilisateurs. 
  
Si vous avez déjà configuré l’authentification de serveur à serveur entre Skype pour Business Server 2015 et 2016 d’Exchange Server ou Exchange Server 2013, vous êtes prêt à configurer la messagerie unifiée. Pour ce faire, vous devez tout d’abord créer et affecter un nouveau plan de numérotation messagerie unifiée sur votre Exchange Server. Par exemple, ces deux commandes (exécuter à partir d’Exchange Management Shell) configurer un nouveau plan de numérotation de 3 chiffres pour Exchange :
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

Dans la première commande de cet exemple, le paramètre VoIPSecurity et la valeur « Secured » du paramètre indiquent que le canal de signalisation est chiffré à l’aide du protocole TLS (Transport Layer Security). La valeur « SipName » de URIType indique que les messages seront envoyés et reçus à l’aide du protocole SIP et la valeur 1 de CountryOrRegionCode signifie que le plan de numérotation s’applique aux États-Unis.
  
Dans la seconde commande, la valeur transmise au paramètre ConfiguredInCountryOrRegionGroups indique quels groupes régionaux peuvent être utilisés avec ce plan de numérotation. La valeur du paramètre « n’importe où,\*,\*,\*"définit les éléments suivants :
  
- Nom du groupe (« Anywhere »)
    
- AllowedNumberString (\*, un caractère générique qui indique que n’importe quelle chaîne numérique est autorisée)
    
- DialNumberString (\*, un caractère générique qui indique que tous les numéros composés sont autorisée)
    
- TextComment (\*, un caractère générique indiquant qu’une commande de texte est autorisée)
    
> [!NOTE]
> Quand vous créez un nouveau plan de numérotation, vous créez aussi une stratégie de boîte aux lettres par défaut. 
  
Après la création et la configuration du nouveau plan de numérotation, vous devez ajouter le nouveau plan à votre serveur de messagerie unifiée de composer et puis modifier le mode de démarrage du serveur ; en particulier, vous devez définir le mode de démarrage « Double ». Vous pouvez effectuer ces tâches à partir d’Exchange Management Shell :
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Après avoir configuré le serveur de messagerie unifié vous devez ensuite exécuter l’applet de commande Enable-ExchangeCertificate pour vous assurer que votre certificat Exchange est appliqué au service de messagerie unifié :
  
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

Si vous disposez d’un second utilisateur, qui a été activé pour la messagerie unifiée, vous pouvez utiliser l’applet de commande [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) pour vérifier que le second utilisateur peut laisser un message de messagerie vocale pour le premier utilisateur.
  
```
$credential = Get-Credential "litwareinc\pilar"

Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```


