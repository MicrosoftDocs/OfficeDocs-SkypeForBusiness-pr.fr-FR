---
title: Planifier l’intégration de Skype Entreprise et d’Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Résumé : consultez cette rubrique pour plus d’informations sur l’intégration de Skype entreprise Server à Exchange Server 2016 ou Exchange Server 2013.'
ms.openlocfilehash: d5d2a50e3b3b376bc27a407313944a31dc1352f6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359260"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Planifier l’intégration de Skype Entreprise et d’Exchange
 
**Résumé :** Consultez cette rubrique pour obtenir des informations sur l’intégration de Skype entreprise Server à Exchange Server 2016 ou Exchange Server 2013.
  
Avant de pouvoir intégrer Skype entreprise Server et Exchange Server, vous devez vous assurer que Exchange Server et Skype entreprise Server sont entièrement installés et en cours d’exécution. 
  
Pour plus d’informations sur l’installation d’Exchange Server, consultez la documentation sur la planification et le déploiement d’Exchange Server pour votre version d’Exchange. 
   
Une fois les serveurs opérationnels, vous devez attribuer des certificats d’authentification de serveur à serveur à Skype entreprise Server et à Exchange Server ; ces certificats permettent à Skype entreprise Server et Exchange Server d’échanger des informations et de communiquer les uns avec les autres. Lorsque vous installez Exchange Server, un certificat auto-signé avec le nom certificat d’authentification Microsoft Exchange Server est créé pour vous. Ce certificat, qui se trouve dans le magasin de certificats de l’ordinateur local, doit être utilisé pour l’authentification de serveur à serveur sur Exchange Server. Pour plus d’informations sur l’attribution de certificats dans Exchange Server, consultez la rubrique [configure mail Flow and Client Access](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Pour Skype entreprise Server, vous pouvez utiliser un certificat Skype entreprise Server existant comme certificat d’authentification de serveur à serveur ; par exemple, votre certificat par défaut peut également être utilisé comme certificat OAuthTokenIssuer. Skype entreprise Server vous permet d’utiliser n’importe quel certificat de serveur Web comme certificat pour l’authentification de serveur à serveur, à condition que :
  
- Le certificat inclut le nom de votre domaine SIP dans le champ Subject.
    
- Le même certificat est configuré comme certificat OAuthTokenIssuer sur tous vos serveurs frontaux.
    
- Le certificat a une longueur d’au moins 2048 bits.
    
Pour plus d’informations sur les certificats d’authentification de serveur à serveur pour Skype entreprise Server, voir [Assign a Server-to-Server Authentication Certificate to Skype for Business Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Une fois les certificats attribués, vous devez configurer le service de découverte automatique sur le serveur Exchange. Dans Exchange Server, le service de découverte automatique configure les profils utilisateur et permet d’accéder aux services Exchange lorsque les utilisateurs se connectent au système. Les utilisateurs présentent le service de découverte automatique avec leur adresse de messagerie et leur mot de passe ; en retour, les services fournissent à l’utilisateur des informations telles que :
  
- Informations de connexion pour la connectivité interne et externe à Exchange Server.
    
- Emplacement du serveur de boîtes aux lettres de l’utilisateur.
    
- URL pour les fonctionnalités Outlook telles que les informations de disponibilité, la messagerie unifiée et le carnet d’adresses en mode hors connexion.
    
- Paramètres du serveur Outlook Anywhere.
    
Le service de découverte automatique doit être configuré pour pouvoir intégrer Skype entreprise Server et Exchange Server. Vous pouvez vérifier si le service de découverte automatique a été configuré en exécutant la commande suivante à partir d’Exchange Server Management Shell et en vérifiant la valeur de la propriété AutoDiscoverServiceInternalUri :
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Si cette valeur est vide, vous devez affecter un URI au service de découverte automatique. En règle générale, cet URI ressemblera à ceci : https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Vous pouvez attribuer l’URI de découverte automatique en exécutant une commande semblable à celle-ci :
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Pour plus d’informations sur le service de découverte automatique, consultez la rubrique [service de découverte automatique](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Après avoir configuré le service de découverte automatique, vous devez modifier les paramètres de configuration OAuth de Skype entreprise Server ; Cela permet de s’assurer que Skype entreprise Server sait où trouver le service de découverte automatique. Pour modifier les paramètres de configuration OAuth dans Skype entreprise Server, exécutez la commande suivante à partir de Skype entreprise Server Management Shell. Lors de l’exécution de cette commande, vérifiez que vous spécifiez l’URI pour le service de découverte automatique qui s’exécute sur votre serveur Exchange et que vous utilisez **autodiscover. svc** pour pointer vers l’emplacement du service au lieu de **autodiscover.xml** (pointant vers le fichier XML utilisé par le service) :
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Le paramètre Identity de la commande précédente est facultatif ; Cela est dû au fait que Skype entreprise Server vous permet d’avoir une seule collection globale de paramètres de configuration OAuth. Cela signifie, entre autres, que vous pouvez configurer l’URL de découverte automatique à l’aide de cette commande légèrement plus simple : 
> 
> [!NOTE]
> Set-applet csoauthconfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> Si vous n’êtes pas familiarisé avec cette technologie, OAuth est un protocole d’autorisation standard utilisé par un certain nombre de sites principaux. Avec OAuth, les informations d’identification de l’utilisateur et les mots de passe ne sont pas transmis d’un ordinateur à un autre. Au lieu de cela, l’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité ; Ces jetons accordent l’accès à un ensemble spécifique de ressources pour une durée spécifique. 
  
En plus de configurer le service de découverte automatique, vous devez également créer un enregistrement DNS pour le service qui pointe vers votre serveur Exchange. Par exemple, si votre service de découverte automatique se trouve dans autodiscover.litwareinc.com, vous devez créer un enregistrement DNS pour autodiscover.litwareinc.com qui se traduit par le nom de domaine complet de votre serveur Exchange (par exemple, atl-exchange-001.litwareinc.com).
  
Si vous intégrez Skype entreprise Server à Exchange Online, les étapes suivantes sont décrites dans [configure Integration between on-premises Skype for Business Server and Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), sinon reportez-vous à la rubrique [intégration de Skype entreprise Server à Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Prise en charge des fonctionnalités
<a name="feature_support"> </a>

>[!Important]
> Skype entreprise Online sera retiré le 31 juillet 2021 une fois que les intégrations Exchange mentionnées ci-dessous, qui incluent le service, ne seront plus prises en charge.

Le tableau suivant détaille les fonctionnalités prises en charge sous différentes combinaisons de en ligne ou en local pour Exchange et Skype entreprise.
  
||**Exchange 2016/2013/2010 (en local) + Skype entreprise Server (en local)**|**Exchange Online + Skype entreprise Server (en local)**|**Exchange 2010 (en local) + Skype entreprise Online**|**Exchange 2016/2013 (sur site) + Skype entreprise Online**|**Exchange Online + Skype entreprise Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Présence dans Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Répondre par messagerie instantanée, appel RTC, appel Skype ou appel vidéo à partir d’un message électronique Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Planification et participation à des réunions en ligne via Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Présence dans Outlook Web App  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Répondre par messagerie instantanée, appel RTC, appel Skype ou appel vidéo à partir d’un e-mail OWA  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Planification et participation à des réunions en ligne via Outlook Web App  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Messagerie instantanée/présence dans les clients mobiles  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Participer à des réunions en ligne dans les clients mobiles  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Publier le statut en fonction des informations de disponibilité du calendrier Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Liste de contacts (par le biais du magasin de contacts unifié)  <br/> |Y (nécessite Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Photo de contact haute résolution (nécessite au minimum les clients Lync 2013 ou Skype entreprise. Non pris en charge pour les applications LWA, mobiles, Lync 2010, Lync pour Mac et d’autres clients plus anciens.)  <br/> |Y (nécessite Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |v  <br/> |v  <br/> |
|Délégation de réunion  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|L’historique des conversations manquées et les journaux d’appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange  <br/> |Y (nécessite Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Recherche de contenu archivé  <br/> |Y (nécessite Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Messagerie vocale Exchange UM  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Historique des conversations côté serveur  <br/> |v  <br/> |v  <br/> |N  <br/> |v  <br/> |v  <br/> |

> [!NOTE]
> Il existe un service de messagerie vocale Cloud qui est pris en charge pour Skype entreprise Online, Skype entreprise Server 2019, Skype entreprise Server 2015 et Lync Server 2013.
> 

## <a name="see-also"></a>Voir aussi
<a name="feature_support"> </a>

[Configurer l’intégration entre Skype entreprise Server local et Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurer OAuth entre Skype entreprise Online et Exchange sur site](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Intégration de Skype entreprise Server à Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Procédure d’intégration d’Exchange Server 2013 avec Lync Server 2013, Skype entreprise Online ou un déploiement hybride Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Configurer des applications partenaires dans Skype entreprise Server et Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
