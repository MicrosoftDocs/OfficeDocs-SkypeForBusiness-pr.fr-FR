---
title: Planifier l’intégration de Skype Entreprise et d’Exchange
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Résumé : Examinez cette rubrique pour plus d’informations sur l’intégration de Skype Entreprise Server avec Exchange Server 2016 ou Exchange Server 2013.'
ms.openlocfilehash: 5edfdf44b50d2a58c097bed5ee83855f375ff895
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2021
ms.locfileid: "61562836"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Planifier l’intégration de Skype Entreprise et d’Exchange
 
**Résumé :** Pour plus d’informations sur l’intégration de Skype Entreprise Server à Exchange Server 2016 ou Exchange Server 2013, voir cette rubrique.
  
Avant de pouvoir intégrer Skype Entreprise Server et Exchange Server, vous devez vous assurer que les Exchange Server et Skype Entreprise Server sont entièrement installés et opérationnels. 
  
Pour plus d’informations sur l’installation Exchange Server, voir la documentation Exchange Server planification et déploiement de votre version de Exchange. 
   
Une fois que les serveurs sont opérationnels, vous devez affecter des certificats d’authentification de serveur à serveur à Skype Entreprise Server et Exchange Server ; ces certificats permettent d’Skype Entreprise Server et Exchange Server  pour échanger des informations et communiquer les uns avec les autres. Lorsque vous installez Exchange Server, un certificat auto-signé nommé certificat Microsoft Exchange Server auth est créé pour vous. Ce certificat, qui se trouve dans le magasin de certificats de l’ordinateur local, doit être utilisé pour l’authentification de serveur à serveur sur Exchange Server. Pour plus d’informations sur l’affectation de certificats dans Exchange Server, voir [Configure Mail Flow and Client Access](/exchange/configure-mail-flow-and-client-access-exchange-2013-help).
  
Par Skype Entreprise Server vous pouvez utiliser un certificat Skype Entreprise Server existant comme certificat d’authentification de serveur à serveur ; par exemple, votre certificat par défaut peut également être utilisé comme certificat OAuthTokenIssuer. Skype Entreprise Server vous permet d’utiliser n’importe quel certificat de serveur Web comme certificat pour l’authentification de serveur à serveur, à condition que :
  
- Le certificat inclut le nom de votre domaine SIP dans le champ Objet.
    
- Le même certificat est configuré en tant que certificat OAuthTokenIssuer sur tous vos serveurs frontaux.
    
- La longueur du certificat est d’au moins 2 048 bits.
    
Pour plus d’informations sur les certificats d’authentification de serveur à serveur pour Skype Entreprise Server, voir [Assign a server-to-server authentication certificate to Skype Entreprise Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Une fois les certificats affectés, vous devez configurer le service de découverte automatique sur Exchange Server. Dans Exchange Server, le service de découverte automatique configure les profils utilisateur et donne accès aux services Exchange lorsque les utilisateurs se connectent au système. Les utilisateurs présentent le service de découverte automatique avec leur adresse de messagerie et leur mot de passe. à leur tour, les services fournissent à l’utilisateur des informations telles que :
  
- Informations de connexion pour la connectivité interne et externe à Exchange Server.
    
- Emplacement du serveur de boîtes aux lettres de l’utilisateur.
    
- URL pour Outlook fonctionnalités telles que les informations de libre/occupé, la messagerie unifiée et le carnet d’adresses en mode hors connexion.
    
- Outlook paramètres du serveur Anywhere.
    
Le service de découverte automatique doit être configuré avant de pouvoir intégrer des Skype Entreprise Server et Exchange Server. Vous pouvez vérifier si le service de découverte automatique a été configuré en exécutant la commande suivante à partir de l’Exchange Server Management Shell et en vérifiant la valeur de la propriété AutoDiscoverServiceInternalUri :
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Si cette valeur est vide, vous devez affecter un URI au service de découverte automatique. En règle générale, cet URI ressemble à ceci : https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Vous pouvez affecter l’URI de découverte automatique en exécutant une commande semblable à celle-ci :
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Pour plus d’informations sur le service de découverte automatique, voir [Service de découverte automatique.](/Exchange/architecture/client-access/autodiscover)
  
Une fois le service de découverte automatique configuré, vous devez modifier les paramètres de configuration OAuth Skype Entreprise Server ; cela garantit que Skype Entreprise Server sait où trouver le service de découverte automatique. Pour modifier les paramètres de configuration OAuth dans Skype Entreprise Server, exécutez la commande suivante à partir de Skype Entreprise Server Management Shell. Lors de l’exécution de cette commande, assurez-vous de spécifier l’URI du service de découverte automatique en cours d’exécution sur votre Exchange Server et d’utiliser **autodiscover.svc** pour pointer vers l’emplacement du service au lieu de **autodiscover.xml** (qui pointe vers le fichier XML utilisé par le service) :
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Le paramètre Identity de la commande précédente est facultatif . En effet, Skype Entreprise Server vous permet uniquement d’avoir une seule collection globale de paramètres de configuration OAuth. Entre autres choses, cela signifie que vous pouvez configurer l’URL de découverte automatique à l’aide de cette commande légèrement plus simple : 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " » 
> 
> [!NOTE]
> Si vous ne connaissez pas la technologie, OAuth est un protocole d’autorisation standard utilisé par de nombreux sites web principaux. Avec OAuth, les informations d’identification et les mots de passe de l’utilisateur ne sont pas transmis d’un ordinateur à un autre. Au lieu de cela, l’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité ; ces jetons accordent l’accès à un ensemble spécifique de ressources pendant une durée spécifique. 
  
Outre la configuration du service de découverte automatique, vous devez également créer un enregistrement DNS pour le service qui pointe vers votre Exchange Server. Par exemple, si votre service de découverte automatique se trouve sur autodiscover.litwareinc.com vous devez créer un enregistrement DNS pour autodiscover.litwareinc.com qui est résolu en nom de domaine complet de votre Exchange Server (par exemple, atl-exchange-001.litwareinc.com).
  
Si vous intégrez Skype Entreprise Server à Exchange Online, vous devez ensuite configurer l’intégration entre Skype Entreprise Server local et [Outlook Web App,](../../deploy/integrate-with-exchange-server/outlook-web-app.md)sinon voir Intégrer [ Skype Entreprise Server avec Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Prise en charge des fonctionnalités
<a name="feature_support"> </a>

>[!Important]
> Skype Entreprise Online a été retiré le 31 juillet 2021. Les Exchange les intégrations répertoriées ci-dessous qui incluent le service ne sont plus pris en charge.

Le tableau suivant détaille les fonctionnalités prise en charge sous différentes combinaisons de fonctionnalités en ligne ou en local pour Exchange et Skype Entreprise.
  
|&nbsp;|Exchange 2016/2013/2010 (local) + Skype Entreprise Server (local)|Exchange Online + Skype Entreprise Server (local)**|**Exchange 2010 (local) + Skype Entreprise Online|Exchange 2016/2013 (local) + Skype Entreprise Online**|**Exchange Online + Skype Entreprise Online|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Présence dans Outlook   |v   |v   |v   |v   |v   |
|Répondre par messagerie instantanée, appel PSTN, appel Skype ou appel vidéo à partir d’un Outlook électronique   |v   |v   |v   |v   |v   |
|Planifier et participer à des réunions en ligne via Outlook   |v   |v   |v   |v   |v   |
|Présence dans Outlook Web App   |v   |v   |N   |N   |v   |
|Répondre par messagerie instantanée, appel PSTN, appel Skype ou appel vidéo à partir d’un OWA électronique   |v   |v   |N   |N   |v   |
|Planifier et participer à des réunions en ligne via Outlook Web App   |v   |v   |N   |N   |v   |
|Messagerie instantanée/présence dans les clients mobiles   |v   |v   |v   |v   |v   |
|Participer à des réunions en ligne dans des clients mobiles   |v   |v   |v   |v   |v   |
|Publier l’état en fonction Outlook informations de libre/occupé du calendrier   |v   |v   |v   |v   |v   |
|Liste des contacts (via le magasin de contacts unifié)   |Y (besoin Exchange 2016/2013)   |v   |N   |N   |v   |
|Photo de contact haute résolution (nécessite Lync 2013 ou Skype Entreprise clients au minimum. Non pris en charge pour LWA, les applications mobiles, Lync 2010, Lync pour Mac et d’autres clients plus anciens.)   |Y (besoin Exchange 2016/2013)   |v   |N   |v   |v   |
|Délégation de réunion   |v   |v   |v   |v   |v   |
|L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur   |v   |v   |v   |v   |v   |
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange   |Y (besoin Exchange 2016/2013)   |v   |N   |N   |v   |
|Rechercher du contenu archivé   |Y (besoin Exchange 2016/2013)   |v   |N   |N   |v   |
|Exchange messagerie vocale de messagerie un peu plus puissante   |v   |v   |N   |N   |N   |
|Historique des conversations côté serveur   |v   |v   |N   |v   |v   |

> [!NOTE]
> Il existe un service Messagerie vocale infonuagique pris en charge pour Skype Entreprise Online, Skype Entreprise Server 2019, Skype Entreprise Server 2015 et Lync Server 2013.
> 

## <a name="see-also"></a>Voir aussi
<a name="feature_support"> </a>

[Configurer l’intégration entre l’application Skype Entreprise Server locale et Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurer OAuth entre Skype Entreprise Online et Exchange local](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Intégrer des Skype Entreprise Server avec Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Comment intégrer Exchange Server 2013 avec Lync Server 2013, Skype Entreprise Online ou un déploiement hybride Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-hybrid-deployments)
  
[Configurer des applications partenaires dans Skype Entreprise Server et Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)