---
title: Intégration à Exchange et SharePoint
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 'Résumé : Découvrez les Skype pour Business Server 2015 l’intégration avec Exchange et SharePoint.'
ms.openlocfilehash: 8d080174ab5560384478c1320d09bc218ef8543b
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530606"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Intégration à Exchange et SharePoint

**Résumé :** Découvrez les Skype pour Business Server 2015 intégration Exchange et SharePoint.

Vous pouvez configurer Skype pour les déploiements Business Server 2015 pour l’intégration avec Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 et SharePoint Server, à la fois sur site et en ligne. Sauf indication contraire, les fonctionnalités affichées dans le tableau ci-dessous sont prises en charge avec tous les clients. Pour plus d’informations sur le client prennent en charge, voir [comparaison des fonctionnalités client de bureau pour Skype pour les entreprises](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) et Skype pour Business en ligne tableau de comparaison des clients au niveau des [Clients pour Skype pour Business Online](https://go.microsoft.com/fwlink/p/?LinkId=281902).

## <a name="integration-with-exchange-server"></a>Intégration à Exchange Server

Les tableaux suivants répertorient les fonctionnalités prises en charge dans un déploiement hybride lorsqu’il est intégré avec Microsoft Exchange Server.

 **Skype pour Business Server sur site et Exchange sur site**


|**Fonctionnalité**|**Remarques**|
|:-----|:-----|
|Messagerie instantanée/présence dans Outlook  <br/> |Pour plus d’informations, voir [messagerie instantanée et présence](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx).  <br/> |
|Planification d’une réunion en ligne et participation à l’aide d’Outlook  <br/> |Pour plus d’informations, voir [Intégration de Skype pour Business Server 2015 avec Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Messagerie instantanée/présence dans Outlook Web App  <br/> |Pour plus d’informations, consultez [configurer un environnement hybride dans Skype pour Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Planification et participer à une réunion en ligne via Outlook Web App  <br/> ||
|Messagerie instantanée/présence dans les clients mobiles  <br/> ||
|Participation à des réunions en ligne dans les clients mobiles  <br/> |Pour plus d’informations, voir [Déploiement de mobilité](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Publication du statut en fonction des informations de disponibilité du calendrier Outlook  <br/> ||
|Liste de contacts (par le biais du magasin de contacts unifié)  <br/> |Requiert Exchange 2016 ou Exchange 2013.  <br/> Skype pour le client de bureau d’entreprise de Lync 2013 est nécessaire.  <br/>  Pour plus d’informations, voir [Configurer les Skype pour Business Server 2015 à utiliser le magasin de contacts unifié](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Photo du Contact haute résolution dans le client Lync 2013, Skype pour Business client et Lync Web App.  <br/> |Requiert Exchange 2016 ou Exchange 2013.  <br/> Pour plus d’informations, voir [Configure l’utilisation de photos haute résolution dans Skype pour Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> |
|Délégation de réunion  <br/> |Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local. Pour plus d’informations, voir [Skype pour des solutions professionnelles hybride](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|L’historique des Conversations et journaux d’appels manqués sont écrites dans la boîte aux lettres exchange de l’utilisateur  <br/> ||
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange  <br/> |Requiert Exchange 2016 ou Exchange 2013.  <br/> Pour plus d’informations, voir [Liste de vérification du déploiement pour l’archivage](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Recherche de contenu archivé  <br/> |Requiert Exchange 2016 ou Exchange 2013.  <br/> |
|Messagerie vocale  <br/> |Pour plus d’informations, voir [Déploiement local la messagerie unifiée Exchange pour fournir la messagerie vocale Lync Server 2013](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |

 **Skype pour Business Server sur site et Exchange Online**


|**Fonctionnalité**|**Remarques**|
|:-----|:-----|
|Messagerie instantanée/présence dans Outlook  <br/> |Pour plus d’informations, voir [configurer l’intégration entre locale Skype pour Business Server 2015 et Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Planification d’une réunion en ligne et participation à l’aide d’Outlook  <br/> ||
|Messagerie instantanée/présence dans Outlook Web App  <br/> |Pour plus d’informations, voir [configurer l’intégration entre locale Skype pour Business Server 2015 et Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Planification et participer à une réunion en ligne à partir d’Outlook Web App  <br/> |Pour plus d’informations, voir [configurer l’intégration entre locale Skype pour Business Server 2015 et Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Messagerie instantanée/présence dans les clients mobiles  <br/> ||
|Participation à une réunion en ligne dans les clients mobiles  <br/> ||
|Publication du statut en fonction des informations de disponibilité du calendrier Outlook  <br/> ||
|Liste de contacts (par le biais du magasin de contacts unifié).  <br/> |Lync Server 2013 uniquement. Skype pour le client de bureau d’entreprise de Lync 2013 est nécessaire.  <br/> Pour plus d’informations, voir [Configurer les Skype pour Business Server 2015 à utiliser le magasin de contacts unifié](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Photo du Contact haute résolution dans le client Lync 2013, Skype pour Business client et Lync Web App.  <br/> |Pour plus d’informations, voir [Configure l’utilisation de photos haute résolution dans Skype pour Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> |
|Délégation de réunion  <br/> |Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local. Pour plus d’informations, voir [Skype pour des solutions professionnelles hybride](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|L’historique des Conversations et journaux d’appels manqués sont écrites dans la boîte aux lettres Exchange de l’utilisateur  <br/> ||
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange  <br/> |Pour plus d’informations, voir [Liste de vérification du déploiement pour l’archivage](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Recherche de contenu archivé  <br/> |Pour plus d’informations, reportez-vous à l’article [Configurer Exchange pour le centre de découverte électronique SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Messagerie vocale  <br/> |Pour plus d’informations, voir [Fournissant Lync Server 2013 messagerie vocale aux utilisateurs de messagerie unifiée Exchange hébergée](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Skype pour Business Online et Exchange sur site**


|**Fonctionnalité**|**Remarques**|
|:-----|:-----|
|Présence dans Outlook  <br/> ||
|Répondre par messagerie instantanée, appel RTC, appel Skype ou appel vidéo dans un e-mail Outlook  <br/> ||
|Planification de réunions en ligne et participation à l’aide d’Outlook  <br/> ||
|Messagerie instantanée/présence dans les clients mobiles  <br/> ||
|Participation à des réunions en ligne dans les clients mobiles  <br/> ||
|Publication du statut en fonction des informations de disponibilité du calendrier Outlook  <br/> ||
|L’historique des Conversations et journaux d’appels manqués sont écrites dans la boîte aux lettres exchange de l’utilisateur  <br/> ||
|Photo du Contact haute résolution dans Lync 2013 ou Skype pour client d’entreprise.  <br/> |Requiert Exchange 2016 ou Exchange 2013. Il n’est pas pris en charge dans Lync Web App lorsque les utilisateurs sont hébergés sur Skype pour Business Online.  <br/> |
|Délégation de réunion  <br/> |Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local. Pour plus d’informations, voir [Skype pour des solutions professionnelles hybride](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|L’historique des Conversations et journaux d’appels manqués sont écrites dans la boîte aux lettres Exchange de l’utilisateur  <br/> ||
|Historique des conversations côté serveur  <br/> ||

 **Skype pour les entreprises en ligne et Exchange Online**


|**Fonctionnalité**|**Remarques**|
|:-----|:-----|
|Messagerie instantanée/présence dans Outlook  <br/> ||
|Planification de réunions en ligne et participation à l’aide d’Outlook  <br/> ||
|Messagerie instantanée/présence dans Outlook Web App  <br/> ||
|Planification et participer à une réunion en ligne à partir d’Outlook Web App  <br/> ||
|Messagerie instantanée/présence dans les clients mobiles  <br/> ||
|Participation à une réunion en ligne dans les clients mobiles  <br/> ||
|Publication du statut en fonction des informations de disponibilité du calendrier Outlook  <br/> ||
|L’historique des Conversations et journaux d’appels manqués sont écrites dans la boîte aux lettres exchange de l’utilisateur  <br/> ||
|Liste de contacts (par le biais du magasin de contacts unifié)  <br/> |Lync Server 2013 ou Skype pour Business client requis  <br/> |
|Haute résolution Photo Contact dans Lync 2013, Skype pour Business client et Lync Web App  <br/> ||
|Délégation de réunion  <br/> |Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local. Pour plus d’informations, voir [Skype pour des solutions professionnelles hybride](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange  <br/> ||
|Recherche de contenu archivé  <br/> ||
|Messagerie vocale  <br/> ||

## <a name="integration-with-sharepoint"></a>Intégration à SharePoint

Le tableau suivant répertorie les fonctionnalités prises en charge dans un déploiement hybride lorsque intégré à SharePoint.

||**SharePoint local**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype pour Business Server 2015 locale** <br/> | Recherche de compétences <br/>  Présence dans SharePoint <br/> | Présence dans SharePoint <br/> |
|**Skype Entreprise Online** <br/> | Présence dans SharePoint <br/> | Présence dans SharePoint <br/> |


