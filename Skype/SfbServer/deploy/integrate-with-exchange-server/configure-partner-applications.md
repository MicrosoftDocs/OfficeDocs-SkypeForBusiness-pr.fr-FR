---
title: Configurer des applications partenaires dans Skype pour Business Server 2015 et Exchange Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Résumé : Configurer l’authentification de serveur à serveur pour 2016 d’Exchange Server ou Exchange Server 2013 et Skype pour Business Server 2015.'
ms.openlocfilehash: d7b3d93126c5b2db06e5f7343f5636b3c305d7c8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-partner-applications-in-skype-for-business-server-2015-and-exchange-server"></a>Configurer des applications partenaires dans Skype pour Business Server 2015 et Exchange Server
 
**Résumé :** Configurer l’authentification de serveur à serveur pour 2016 d’Exchange Server ou Exchange Server 2013 et Skype pour Business Server 2015.
  
L’authentification serveur à serveur requiert généralement deux serveurs qui doivent communiquer l’un avec l’autre et un serveur d’émission de jetons de sécurité tiers. Si le serveur A et le serveur B doivent communiquer, puis tous les deux de ces serveurs commencez généralement par contacter un serveur de jeton et l’obtention d’un jeton de sécurité d’un niveau de confiance mutuellement. Le Serveur A présente ensuite ce jeton de sécurité au Serveur B (et inversement) afin de prouver son authenticité et sa fiabilité.
  
Toutefois, c’est la règle générale. Skype pour Business Server 2015, 2016 d’Exchange Server, Exchange Server 2013 et SharePoint Server 2013 n’avez pas besoin d’utiliser un serveur de jeton de tiers lors de la communication avec l’autre ; C’est parce que ces produits de serveur peuvent créer des jetons de sécurité qui peuvent être acceptés par un autre sans avoir besoin d’un serveur distinct de jeton. (Cette fonctionnalité est uniquement disponible dans Skype pour Business Server 2015, 2016 d’Exchange Server, Exchange Server 2013 et SharePoint Server 2013. Si vous avez besoin configurer l’authentification de serveur à serveur avec d’autres serveurs, y compris d’autres produits serveur Microsoft, puis vous devrez faire à l’aide d’un serveur de jeton de tierce partie.)
  
Pour configurer l’authentification de serveur à serveur entre Skype pour Business Server et Exchange Server, vous devez faire deux choses : 1) vous devez attribuer les certificats appropriés à chaque serveur ; et 2) vous devez configurer chaque serveur pour une application de partenaire de l’autre serveur : cela signifie que vous devez configurer Skype pour 2015 de serveur d’entreprise d’une application de partenaires pour Exchange Server, et vous devez configurer Exchange Server pour une application de partenaire pour Skype pour Business Server 2015.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configuration de Skype pour Business Server pour une Application de partenaires pour Exchange Server

La façon la plus simple pour configurer Skype pour 2015 de serveur métier d’une application de partenaire avec 2016 d’Exchange Server ou Exchange Server 2013 est d’exécuter le script de configuration-EnterprisePartnerApplication.ps1, un script Windows PowerShell qui est fourni avec Exchange Server . Pour exécuter ce script, vous devez fournir l’URL de la Skype pour le document de métadonnées de l’authentification de serveur de l’entreprise ; Ce sera généralement le nom de domaine complet de la Skype pour le pool d’entreprise serveur 2015 suivie par le suffixe /metadata/json/1. Par exemple :
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Pour configurer Business Server en tant que demande de partenariat Skype, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci (en supposant que Exchange a été installé sur le lecteur C: et qu’il utilise le chemin d’accès du dossier par défaut) :
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Après avoir configuré l’application partenaire il est recommandé d’arrêter et de redémarrer Internet Information Services (IIS) sur vos serveurs d’accès client et boîte aux lettres Exchange. Vous pouvez redémarrer IIS à l’aide d’une commande semblable à la suivante, qui redémarre le service sur l’ordinateur atl-exchange-001 :
  
```
iisreset atl-exchange-001
```

Cette commande peut être exécutée à partir d’Exchange Management Shell ou de toute autre fenêtre de commande s’exécutent sous des privilèges d’administrateur.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Configuration d’Exchange Server à une application du partenaire pour Skype pour Business Server

Après avoir configuré Skype pour 2015 de serveur métier d’une application du partenaire pour 2016 d’Exchange Server ou Exchange Server 2013, vous devez alors configurer Exchange Server pour une application de partenaire pour Skype pour Business Server. Ceci est possible en utilisant le Skype pour Business Server Management Shell et en spécifiant le document de métadonnées d’authentification pour Exchange ; Il s’agit généralement de l’URI du service de découverte automatique Exchange suivi par le suffixe /metadata/json/1. Par exemple :
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

Dans Skype pour Business Server, les applications partenaires sont configurées à l’aide de l’applet de commande [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) . En plus de spécifier l’URI de métadonnées vous devez également définir l’approbation d’application au niveau complet ; Cela permettra à Exchange représenter lui-même et tout utilisateur autorisé dans le domaine. Par exemple :
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Vous pouvez également créer une application de partenaire en copiant et en modifiant le code de script dans le Skype pour la documentation de l’authentification de serveur à serveur Business Server 2015. Consultez l’article de [gérer l’authentification de serveur à serveur (OAuth) et les applications partenaires dans Skype pour Business Server 2015](../../manage/authentication/server-to-server-and-partner-applications.md) pour plus d’informations.
  
Si vous avez configuré avec succès des applications de partenaires pour les deux Skype pour Business Server et Exchange Server, vous avez également correctement configuré l’authentification de serveur à serveur entre les deux produits. Skype pour Business Server 2015 inclut une applet de commande Windows PowerShell, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) qui permet de vérifier que l’authentification de serveur à serveur n’a pas été correctement configurée et que le Skype pour le Service de stockage Business Server peut se connecter à Exchange Server. L’applet de commande pour cela se connecter à la boîte aux lettres d’un utilisateur Exchange Server, l’écriture d’un élément dans le dossier historique des conversations pour cet utilisateur et ensuite (éventuellement) la suppression de cet élément.
  
Pour tester l’intégration de Skype pour Business Server 2015 et Exchange Server, exécutez une commande semblable à la suivante à partir de la Skype pour Business Server Management Shell :
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

Dans la commande précédente, le SipUri représente l’adresse SIP d’un utilisateur ayant un compte sur Exchange Server, ; votre commande échouera dans il ne s’agit pas d’un compte d’utilisateur valide.
  
> [!NOTE]
> Si vous recevez une réponse 401 à partir de cette applet de commande, c’est probablement parce que la configuration par défaut pour Exchange n’inclut pas de prise en charge pour l’acceptation des jetons de Oauth. Pour plus d’informations sur l’utilisation de Oauth dans Exchange, consultez [authentification OAuth de configurer avec SharePoint 2013 et Skype pour Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkId=513103). 
  
Si le test réussit et que la connectivité a été établie, vous pouvez passer à la configuration de fonctionnalités facultatives telles que l’intégration de l’archivage et le magasin de contacts unifié.
  

