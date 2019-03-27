---
title: Configurer des applications partenaires Skype pour Business Server 2015 et Exchange Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Résumé : Configurez l’authentification de serveur à serveur pour Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server.'
ms.openlocfilehash: d9d2b32b637946555b906f24e7abbd5dda007d7f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878472"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Configurer des applications partenaires Skype pour Business Server et Exchange Server
 
**Résumé :** Configurer l’authentification de serveur à serveur pour Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server.
  
L’authentification serveur à serveur requiert généralement deux serveurs qui doivent communiquer l’un avec l’autre et un serveur d’émission de jetons de sécurité tiers. Si le serveur A et serveur B doivent communiquer, puis les deux de ces serveurs généralement démarrer à contacter un serveur de jetons et d’obtenir un jeton de sécurité mutuellement approuvés. Le Serveur A présente ensuite ce jeton de sécurité au Serveur B (et inversement) afin de prouver son authenticité et sa fiabilité.
  
Toutefois, qui est une règle générale. Skype pour Business Server, Exchange Server 2016, Exchange Server 2013 et SharePoint Server 2013 n’avez pas besoin d’utiliser un serveur de jetons tiers lors de la communication entre eux ; C’est parce que ces produits serveur peuvent créer des jetons de sécurité qui peuvent être acceptées par l’autre, sans la nécessité d’un serveur de jetons distinct. (Cette fonctionnalité est uniquement disponible dans Skype pour Business Server, Exchange Server 2016, Exchange Server 2013 et SharePoint Server 2013. Si vous avez besoin configurer l’authentification de serveur à serveur avec d’autres serveurs, y compris d’autres produits serveur Microsoft, puis vous devrez le faire à l’aide d’un serveur de jetons tierce.)
  
Pour configurer l’authentification de serveur à serveur entre Skype pour Business Server et Exchange Server, vous devez effectuer deux opérations : 1) vous devez assigner les certificats appropriés à chaque serveur ; et, 2) vous devez configurer chaque serveur pour une application partenaire de l’autre serveur : cela signifie que vous devez configurer Skype pour Business Server comme application partenaire pour Exchange Server, et vous devez configurer Exchange Server pour une application partenaire pour Skype pour un serveur d’entreprise.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configuration de Skype pour Business Server comme Application partenaire pour Exchange Server

Pour configurer Skype pour Business Server comme application partenaire avec Exchange Server 2016 ou Exchange Server 2013, la plus simple consiste à exécuter le script Configure-enterprisepartnerapplication.ps1, un script Windows PowerShell qui est fourni avec Exchange Server. Pour exécuter ce script, vous devez fournir l’URL pour le Skype pour le document de métadonnées d’authentification Business Server ; Il sera généralement le nom de domaine complet de le Skype pour Business Server pool suivi du suffixe /metadata/json/1. Par exemple :
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Pour configurer Business Server comme application partenaire Skype, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci (en supposant que Exchange a été installé sur le lecteur c, et qu’elle utilise le chemin d’accès du dossier par défaut) :
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Après avoir configuré l’application partenaire, il est recommandé que vous arrêtez et redémarrez Internet Information Services (IIS) sur vos serveurs d’accès client et boîte aux lettres Exchange. Vous pouvez redémarrer IIS à l’aide d’une commande semblable à la suivante, qui redémarre le service sur l’ordinateur atl-exchange-001 :
  
```
iisreset atl-exchange-001
```

Cette commande peut être exécutée à partir de l’environnement Exchange Management Shell ou depuis toute fenêtre de commande s’exécutent sous privilèges d’administrateur.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Configuration d’Exchange Server pour une Application partenaire pour Skype pour Business Server

Une fois que vous avez configuré Skype pour Business Server comme application partenaire pour Exchange Server 2016 ou Exchange Server 2013, vous devez ensuite configurer Exchange Server pour une application partenaire pour Skype pour Business Server. Cela en utilisant la Skype pour Business Server Management Shell et en spécifiant le document de métadonnées d’authentification pour Exchange ; Il s’agit généralement de l’URI du service de découverte automatique Exchange suivi par le suffixe /metadata/json/1. Par exemple :
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

Dans Skype pour Business Server, les applications partenaires sont configurées à l’aide de l’applet de commande [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) . Outre la spécification de l’URI de métadonnées vous devez également définir l’approbation d’application au niveau Full ; Cela permettra Exchange représenter elle-même et n’importe quel utilisateur autorisé dans le domaine. Par exemple :
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Sinon, vous pouvez créer une application partenaire en copiant et modification du code de script, voir le Skype pour la documentation d’authentification de serveur à serveur Business Server. Consultez l’article [gérer l’authentification de serveur à serveur (OAuth) et des applications partenaires dans Skype pour Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) pour plus d’informations.
  
Si vous avez configuré correctement les applications partenaires pour les deux Skype pour Business Server et Exchange Server, vous avez également correctement configuré l’authentification de serveur à serveur entre les deux produits. Skype pour Business Server inclut une applet de commande Windows PowerShell, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) qui vous permet de vérifier que l’authentification de serveur à serveur a été correctement configurée et que la Skype pour le Service de stockage Business Server peut Connectez-vous au serveur Exchange. L’applet de commande effectue cette action en se connectant à la boîte aux lettres d’un utilisateur Exchange Server, écriture d’un élément dans le dossier historique des conversations de cet utilisateur, puis supprimez (le cas échéant) que cet élément.
  
Pour tester l’intégration de Skype pour Business Server et Exchange Server, exécutez une commande semblable à ce qui suit à partir de la Skype pour Business Server Management Shell :
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

Dans la commande précédente, SipUri représente l’adresse SIP d’un utilisateur avec un compte sur le serveur Exchange. votre commande échouera dans ce n’est pas un compte d’utilisateur valide.
  
> [!NOTE]
> Si vous recevez une réponse 401 à partir de cette applet de commande, c’est probablement que la configuration par défaut pour Exchange n’inclut pas de prise en charge pour accepter les jetons Oauth. Pour plus d’informations sur l’utilisation d’Oauth dans Exchange, voir [authentification OAuth configurer avec SharePoint 2013 et Skype pour Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103). 
  
Si le test réussit et que la connectivité a été établie, vous pouvez passer à la configuration de fonctionnalités facultatives telles que l’intégration de l’archivage et le magasin de contacts unifié.
