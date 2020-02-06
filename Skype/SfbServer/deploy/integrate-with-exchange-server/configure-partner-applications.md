---
title: Configurer les applications partenaires dans Skype entreprise Server 2015 et Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Résumé : configurez l’authentification de serveur à serveur pour Exchange Server 2016 ou Exchange Server 2013 et Skype entreprise Server.'
ms.openlocfilehash: 9512d271b23f26afcb1ef6385a1a6dd5d513c948
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797075"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Configurer les applications partenaires dans Skype entreprise Server et Exchange Server
 
**Résumé :** Configurer l’authentification de serveur à serveur pour Exchange Server 2016 ou Exchange Server 2013 et Skype entreprise Server.
  
L’authentification serveur à serveur requiert généralement deux serveurs qui doivent communiquer l’un avec l’autre et un serveur d’émission de jetons de sécurité tiers. Si les serveurs A et B doivent communiquer, les deux serveurs sont généralement à l’aide d’un serveur de jetons et de l’obtention d’un jeton de sécurité digne de confiance. Le Serveur A présente ensuite ce jeton de sécurité au Serveur B (et inversement) afin de prouver son authenticité et sa fiabilité.
  
Néanmoins, il s’agit d’une règle générale. Skype entreprise Server, Exchange Server 2016, Exchange Server 2013 et SharePoint Server 2013 n’ont pas besoin d’utiliser un serveur à jeton tiers pour communiquer entre eux. ce n’est pas parce que ces produits serveur peuvent créer des jetons de sécurité qui peuvent être acceptés l’un de l’autre sans qu’il soit nécessaire de recourir à un serveur jeton distinct. (Cette fonctionnalité est disponible uniquement dans Skype entreprise Server, Exchange Server 2016, Exchange Server 2013 et SharePoint Server 2013. Si vous avez besoin de configurer l’authentification serveur à serveur avec d’autres serveurs, y compris d’autres produits Microsoft Server, vous devez le faire à l’aide d’un serveur de jetons tiers.)
  
Pour configurer l’authentification de serveur à serveur entre Skype entreprise Server et Exchange Server, vous devez effectuer deux opérations : 1) vous devez attribuer les certificats appropriés à chaque serveur. et 2) vous devez configurer chaque serveur pour qu’il s’agit d’une application partenaire de l’autre serveur : cela signifie que vous devez configurer Skype entreprise Server en tant qu’application partenaire pour Exchange Server et que vous devez configurer Exchange Server en tant qu’application partenaire pour Skype. pour Business Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configuration de Skype entreprise Server en tant qu’application partenaire pour Exchange Server

Le moyen le plus simple de configurer Skype entreprise Server en tant qu’application partenaire avec Exchange Server 2016 ou Exchange Server 2013 consiste à exécuter le script Configure-EnterprisePartnerApplication. ps1, un script Windows PowerShell fourni avec Exchange Server. Pour exécuter ce script, vous devez indiquer l’URL du document de métadonnées d’authentification de Skype entreprise Server. Il s’agit généralement du nom de domaine complet du pool Skype entreprise Server suivi du suffixe/Metadata/JSON/1. Par exemple :
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Pour configurer Skype entreprise Server en tant qu’application partenaire, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci (en partant du principe que Exchange a été installé sur le lecteur C, et qu’il utilise le chemin d’accès du dossier par défaut) :
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Après avoir configuré l’application partenaire, il est recommandé d’arrêter et de redémarrer Internet Information Services (IIS) sur votre boîte aux lettres Exchange et les serveurs d’accès au client. Vous pouvez redémarrer IIS à l’aide d’une commande semblable à la suivante, qui redémarre le service sur l’ordinateur atl-exchange-001 :
  
```powershell
iisreset atl-exchange-001
```

Vous pouvez exécuter cette commande à partir de Exchange Management Shell ou de n’importe quelle autre fenêtre de commande sous privilèges d’administrateur.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Configuration d’Exchange Server en tant qu’application partenaire pour Skype entreprise Server

Une fois que vous avez configuré Skype entreprise Server comme application partenaire pour Exchange Server 2016 ou Exchange Server 2013, vous devez alors configurer Exchange Server comme application partenaire pour Skype entreprise Server. Vous pouvez effectuer cette opération à l’aide de Skype entreprise Server Management Shell et en spécifiant le document de métadonnées d’authentification pour Exchange. Il s’agit généralement de l’URI du service de découverte automatique Exchange suivi du suffixe/Metadata/JSON/1. Par exemple :
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

Dans Skype entreprise Server, les applications partenaires sont configurées à l’aide de l’applet [de nouvelle applet de nouveau-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) . En plus de spécifier l’URI de métadonnées, vous devez également définir le niveau de confiance application sur complet. Cela permet à Exchange de représenter eux-mêmes et tout utilisateur autorisé du domaine. Par exemple :
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Vous pouvez également créer une application partenaire en copiant et en modifiant le code de script figurant dans la documentation relative à l’authentification de serveur à serveur Skype entreprise Server. Pour plus d’informations, reportez-vous à la section [gérer l’authentification de serveur à serveur (OAuth) et aux applications partenaires dans l’article Skype entreprise Server](../../manage/authentication/server-to-server-and-partner-applications.md) .
  
Si vous avez correctement configuré des applications de partenariat pour Skype entreprise Server et Exchange Server, vous avez correctement configuré l’authentification de serveur à serveur entre les deux produits. Skype entreprise Server inclut une cmdlet Windows PowerShell, [test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) qui vous permet de vérifier que l’authentification de serveur à serveur est correctement configurée et que le service de stockage de Skype entreprise Server peut se connecter au serveur Exchange. Cette applet de commande permet de se connecter à la boîte aux lettres d’un utilisateur du serveur Exchange, de l’écrire dans le dossier historique des conversations de cet utilisateur, puis de le supprimer.
  
Pour tester l’intégration de Skype entreprise Server et Exchange Server, exécutez une commande similaire à celle qui suit dans Skype entreprise Server Management Shell :
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

Dans la commande précédente, SipUri représente l’adresse SIP d’un utilisateur disposant d’un compte sur le serveur Exchange Server. Il n’existe pas de compte d’utilisateur valide pour votre commande.
  
> [!NOTE]
> Si vous recevez une réponse 401 de cette cmdlet, c’est probablement parce que la configuration par défaut pour Exchange n’inclut pas de prise en charge de l’acceptation des jetons OAuth. Pour plus d’informations sur l’utilisation de OAuth dans Exchange, voir [configurer l’authentification OAuth avec SharePoint 2013 et Skype entreprise Server](https://go.microsoft.com/fwlink/p/?LinkId=513103). 
  
Si le test réussit et que la connectivité a été établie, vous pouvez passer à la configuration de fonctionnalités facultatives telles que l’intégration de l’archivage et le magasin de contacts unifié.
