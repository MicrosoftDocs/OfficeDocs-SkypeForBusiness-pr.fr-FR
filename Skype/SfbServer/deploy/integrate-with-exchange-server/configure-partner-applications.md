---
title: Configurer des applications partenaires dans Skype Entreprise Server 2015 et Exchange Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Résumé : Configurez l’authentification de serveur à serveur pour Exchange Server 2016 ou Exchange Server 2013 et Skype Entreprise Server.'
ms.openlocfilehash: 0f85c617558ae348eaa554efcb5aff1fb4a624d2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771462"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Configurer des applications partenaires dans Skype Entreprise Server et Exchange Server
 
**Résumé :** Configurez l’authentification de serveur à serveur pour Exchange Server 2016 ou Exchange Server 2013 et Skype Entreprise Server.
  
L’authentification de serveur à serveur nécessite généralement deux serveurs qui doivent communiquer entre eux et un serveur de jetons de sécurité tiers. Si le serveur A et le serveur B doivent communiquer, ces deux serveurs commencent généralement par contacter un serveur de jetons et obtenir un jeton de sécurité approuvé mutuellement. Le serveur A présente ensuite ce jeton de sécurité au serveur B (et vice versa) pour garantir son authenticité et sa fiabilité.
  
Ceci n’est toutefois qu’une règle générale. Skype Entreprise Server, Exchange Server 2016, Exchange Server 2013 et SharePoint Server 2013 n’ont pas besoin d’utiliser un serveur de jetons tiers pour communiquer entre eux ; Cela est dû au fait que ces produits serveur peuvent créer des jetons de sécurité qui peuvent être acceptés les uns par les autres sans avoir besoin d’un serveur de jetons distinct. (Cette fonctionnalité est disponible uniquement dans Skype Entreprise Server, Exchange Server 2016, Exchange Server 2013 et SharePoint Server 2013. Si vous devez configurer l’authentification de serveur à serveur avec d’autres serveurs, y compris d’autres produits serveurs Microsoft, vous devrez faire appel à un serveur d’émission de jetons tiers.)
  
Pour configurer l’authentification de serveur à serveur entre Skype Entreprise Server et Exchange Server vous devez faire deux choses : 1) vous devez affecter les certificats appropriés à chaque serveur ; et, 2) vous devez configurer chaque serveur pour qu’il soit une application partenaire de l’autre serveur : cela signifie que vous devez configurer Skype Entreprise Server en tant qu’application partenaire pour Exchange Server et que vous devez configurer Exchange Server en tant qu’application partenaire pour Skype Entreprise Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configuration Skype Entreprise Server être une application partenaire pour Exchange Server

Le moyen le plus simple de configurer Skype Entreprise Server en tant qu’application partenaire avec Exchange Server 2016 ou Exchange Server 2013 consiste à exécuter le script Configure-EnterprisePartnerApplication.ps1, un script Windows PowerShell qui est Exchange Server. Pour exécuter ce script, vous devez fournir l’URL du document de métadonnées Skype Entreprise Server’authentification de l’utilisateur . Il s’agit généralement du nom de domaine complet du pool Skype Entreprise Server suivi du suffixe /metadata/json/1. Par exemple :
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Pour configurer Skype Entreprise Server en tant qu’application partenaire, ouvrez l’Exchange Management Shell et exécutez une commande semblable à celle-ci (en supposant que Exchange a été installé sur le lecteur C: et qu’il utilise le chemin d’accès du dossier par défaut) :
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Après avoir configuré l’application partenaire, il est recommandé d’arrêter et de redémarrer Internet Information Services (IIS) sur vos serveurs de boîtes aux lettres Exchange et d’accès au client. Vous pouvez redémarrer les services Internet (IIS) à l’aide d’une commande ressemblant à celle-ci, qui permet de redémarrer le service sur l’ordinateur atl-exchange-001 :
  
```powershell
iisreset atl-exchange-001
```

Cette commande peut être exécuté à partir de l’Exchange Management Shell ou de toute autre fenêtre de commande s’exécuter sous des privilèges d’administrateur.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Configuration Exchange Server être une application partenaire pour Skype Entreprise Server

Après avoir configuré Skype Entreprise Server en tant qu’application partenaire pour Exchange Server 2016 ou Exchange Server 2013, vous devez configurer Exchange Server en tant qu’application partenaire pour Skype Entreprise Server. Pour ce faire, vous pouvez utiliser l’Skype Entreprise Server Management Shell et spécifier le document de métadonnées d’authentification pour Exchange ; Il s’agit généralement de l’URI Exchange service de découverte automatique suivi du suffixe /metadata/json/1. Par exemple :
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

Dans Skype Entreprise Server, les applications partenaires sont configurées à l’aide de l’cmdlet [New-CsPartnerApplication.](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) En plus de spécifier l’URI des métadonnées, vous devez également définir le niveau de confiance de l’application sur Complet . Cela permet aux Exchange de représenter à la fois lui-même et tout utilisateur autorisé dans le domaine. Par exemple :
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Vous pouvez également créer une application partenaire en copiant et en modifiant le code de script trouvé dans la documentation Skype Entreprise Server’authentification de serveur à serveur. Pour plus d’informations, voir l’article Gérer l’authentification de serveur à serveur [(OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) et les applications partenaires Skype Entreprise Server’article.
  
Si vous avez correctement configuré les applications partenaires pour Skype Entreprise Server et Exchange Server, vous avez également configuré l’authentification de serveur à serveur entre les deux produits. Skype Entreprise Server comprend une cmdlet Windows PowerShell, [Test-CsExStorageConnectivity,](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) qui vous permet de vérifier que l’authentification de serveur à serveur a été correctement configurée et que le service Skype Entreprise Server Stockage peut se connecter à Exchange Server. Pour ce faire, la cmdlet se connecte à la boîte aux lettres d’un utilisateur Exchange Server, écrit un élément dans le dossier Historique des conversations de cet utilisateur, puis la suppression (facultative) de cet élément.
  
Pour tester l’intégration de Skype Entreprise Server et Exchange Server, exécutez une commande semblable à la suivante à partir de Skype Entreprise Server Management Shell :
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

Dans la commande précédente, sipUri représente l’adresse SIP d’un utilisateur avec un compte sur Exchange Server; votre commande échouera dans ce compte d’utilisateur non valide.
  
> [!NOTE]
> Si vous recevez une réponse 401 de cette cmdlet, c’est probablement parce que la configuration par défaut de Exchange n’inclut pas la prise en charge de l’acceptation des jetons Oauth. Pour plus d’informations sur l’utilisation d’Oauth dans Exchange, voir [Configurer l’authentification OAuth avec SharePoint 2013 et Skype Entreprise Server](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help). 
  
Si le test réussit et que la connectivité a été établie, vous pouvez passer à la configuration de fonctionnalités facultatives telles que l’intégration de l’archivage et le magasin de contacts unifié.