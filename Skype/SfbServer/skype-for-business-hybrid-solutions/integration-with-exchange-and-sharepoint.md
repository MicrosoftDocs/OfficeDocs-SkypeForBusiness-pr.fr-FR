---
title: Intégration avec Exchange et SharePoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 'Résumé : en savoir plus sur l’intégration de Skype entreprise Server 2015 à Exchange et SharePoint.'
ms.openlocfilehash: 18839125faee2dfd27ad3843e37b723f56581ff3
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231145"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Intégration avec Exchange et SharePoint

**Résumé :** En savoir plus sur l’intégration de Skype entreprise Server 2015 à Exchange et SharePoint.

Vous pouvez configurer les déploiements de Skype entreprise Server 2015 à des fins d’intégration avec Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 et SharePoint Server, en local et en ligne. Sauf indication contraire, les fonctionnalités affichées dans le tableau ci-dessous sont prises en charge avec tous les clients. Pour plus d’informations sur la prise en charge du client, reportez-vous à la rubrique [comparaison des fonctionnalités du client de bureau pour Skype entreprise](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) et comparaison des clients Skype entreprise Online aux [clients de Skype entreprise Online](https://go.microsoft.com/fwlink/p/?LinkId=281902).

## <a name="integration-with-exchange-server"></a>Intégration à Exchange Server

Les tableaux suivants répertorient les fonctionnalités prises en charge dans un déploiement hybride lors de l’intégration avec Microsoft Exchange Server.

 **Skype entreprise Server en local et Exchange en local**


|**Fonctionnalité**|**Remarques**|
|:-----|:-----|
|Messagerie instantanée/présence dans Outlook  <br/> |Pour plus d’informations, consultez la section [messagerie instantanée et présence](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx).  <br/> |
|Planification d’une réunion en ligne et participation à l’aide d’Outlook  <br/> |Pour plus d’informations, reportez-vous à [intégration de Skype entreprise Server 2015 à Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Messagerie instantanée et présence dans Outlook Web App  <br/> |Pour plus d’informations, reportez-vous à [la rubrique Configuration d’un environnement hybride dans Skype entreprise Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Planifier et participer à une réunion en ligne via Outlook Web App  <br/> ||
|Messagerie instantanée/présence dans les clients mobiles  <br/> ||
|Participation à des réunions en ligne dans les clients mobiles  <br/> |Pour plus d’informations, reportez-vous à la rubrique [déploiement de mobilité](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Publication du statut en fonction des informations de disponibilité du calendrier Outlook  <br/> ||
|Liste de contacts (par le biais du magasin de contacts unifié)  <br/> |Nécessite Exchange 2016 ou Exchange 2013.  <br/> Un client de bureau Lync 2013 ou Skype entreprise est nécessaire.  <br/>  Pour plus d’informations, reportez-vous [à configurer Skype entreprise Server 2015 pour utiliser le magasin de contacts unifié](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Une photo de contact haute résolution dans le client Lync 2013, le client Skype entreprise et Lync Web App.  <br/> |Nécessite Exchange 2016 ou Exchange 2013.  <br/> Pour plus d’informations, reportez-vous à [la rubrique Configuration de l’utilisation de photos haute résolution dans Skype entreprise Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Dans le cadre de l’application Skype entreprise pour MAC et de l’application mobile, l’intégration de Skype entreprise Server 2015 et Exchange Server doit être configurée comme décrit dans la rubrique [configurer les applications partenaires de Skype entreprise Server et Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md). <br/> |
|Délégation de réunion  <br/> |Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local. Pour plus d’informations, reportez-vous à la rubrique [solutions hybrides Skype entreprise](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|L’historique des conversations manquées et les journaux d’appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur  <br/> ||
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange  <br/> |Nécessite Exchange 2016 ou Exchange 2013.  <br/> Pour plus d’informations, voir [liste de vérification de déploiement pour l’archivage](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Recherche de contenu archivé  <br/> |Nécessite Exchange 2016 ou Exchange 2013.  <br/> |
|Messagerie vocale  <br/> |Pour plus d’informations, reportez-vous à la rubrique [déploiement de la messagerie unifiée Exchange locale pour fournir la messagerie vocale Lync Server 2013](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |

 **Skype entreprise Server en local et Exchange Online**


|**Fonctionnalité**|**Remarques**|
|:-----|:-----|
|Messagerie instantanée/présence dans Outlook  <br/> |Pour plus d’informations, reportez-vous à la rubrique Configuration de l' [intégration entre Skype entreprise Server 2015 et Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Planification d’une réunion en ligne et participation à l’aide d’Outlook  <br/> ||
|Messagerie instantanée et présence dans Outlook Web App  <br/> |Pour plus d’informations, reportez-vous à la rubrique Configuration de l' [intégration entre Skype entreprise Server 2015 et Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Planifier et rejoindre une réunion en ligne à partir d’Outlook Web App  <br/> |Pour plus d’informations, reportez-vous à la rubrique Configuration de l' [intégration entre Skype entreprise Server 2015 et Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Messagerie instantanée/présence dans les clients mobiles  <br/> ||
|Participation à une réunion en ligne dans les clients mobiles  <br/> ||
|Publication du statut en fonction des informations de disponibilité du calendrier Outlook  <br/> ||
|Liste de contacts (par le biais du magasin de contacts unifié).  <br/> |Lync Server 2013 uniquement. Un client de bureau Lync 2013 ou Skype entreprise est nécessaire.  <br/> Pour plus d’informations, reportez-vous [à configurer Skype entreprise Server 2015 de façon à utiliser le magasin de contacts unifié](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Une photo de contact haute résolution dans le client Lync 2013, le client Skype entreprise et Lync Web App.  <br/> |Pour plus d’informations, reportez-vous à [la rubrique Configuration de l’utilisation de photos haute résolution dans Skype entreprise Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Pour les photos dans l’application Skype entreprise pour MAC et les appareils mobiles, l’intégration entre Skype entreprise Server 2015 et Exchange Server doit être configurée comme décrit dans la rubrique [configurer l’intégration entre Skype entreprise Server et Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md). <br/> |
|Délégation de réunion  <br/> |Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local. Pour plus d’informations, reportez-vous à la rubrique [solutions hybrides Skype entreprise](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|L’historique des conversations manquées et les journaux d’appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur  <br/> ||
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange  <br/> |Pour plus d’informations, voir [liste de vérification de déploiement pour l’archivage](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Recherche de contenu archivé  <br/> |Pour plus d’informations, reportez-vous à la section [configurer Exchange pour le centre de découverte électronique SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Messagerie vocale  <br/> |Pour plus d’informations, reportez-vous à la section [fourniture de messages vocaux aux utilisateurs Lync Server 2013 sur la messagerie unifiée Exchange](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Skype entreprise Online et Exchange en local**


|**Fonctionnalité**|**Remarques**|
|:-----|:-----|
|Présence dans Outlook  <br/> ||
|Répondre par messagerie instantanée, appel RTC, appel Skype ou appel vidéo dans un e-mail Outlook  <br/> ||
|Planification de réunions en ligne et participation à l’aide d’Outlook  <br/> ||
|Messagerie instantanée/présence dans les clients mobiles  <br/> ||
|Participation à des réunions en ligne dans les clients mobiles  <br/> ||
|Publication du statut en fonction des informations de disponibilité du calendrier Outlook  <br/> ||
|L’historique des conversations manquées et les journaux d’appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur  <br/> ||
|Photo de contact haute résolution dans Lync 2013 ou client Skype entreprise.  <br/> |Nécessite Exchange 2016 ou Exchange 2013. Ceci n’est pas pris en charge dans Lync Web App lorsque les utilisateurs sont familiaux dans Skype entreprise online.  <br/> |
|Délégation de réunion  <br/> |Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local. Pour plus d’informations, reportez-vous à la rubrique [solutions hybrides Skype entreprise](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|L’historique des conversations manquées et les journaux d’appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur  <br/> ||
|Historique des conversations côté serveur  <br/> ||

 **Skype entreprise Online et Exchange Online**


|**Fonctionnalité**|**Remarques**|
|:-----|:-----|
|Messagerie instantanée/présence dans Outlook  <br/> ||
|Planification de réunions en ligne et participation à l’aide d’Outlook  <br/> ||
|Messagerie instantanée et présence dans Outlook Web App  <br/> ||
|Planifier et rejoindre une réunion en ligne à partir d’Outlook Web App  <br/> ||
|Messagerie instantanée/présence dans les clients mobiles  <br/> ||
|Participation à une réunion en ligne dans les clients mobiles  <br/> ||
|Publication du statut en fonction des informations de disponibilité du calendrier Outlook  <br/> ||
|L’historique des conversations manquées et les journaux d’appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur  <br/> ||
|Liste de contacts (par le biais du magasin de contacts unifié)  <br/> |Client Lync Server 2013 ou Skype entreprise requis  <br/> |
|Photo de contact haute résolution dans Lync 2013, client Skype entreprise et Lync Web App  <br/> ||
|Délégation de réunion  <br/> |Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local. Pour plus d’informations, reportez-vous à la rubrique [solutions hybrides Skype entreprise](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange  <br/> ||
|Recherche de contenu archivé  <br/> ||
|Messagerie vocale  <br/> ||

## <a name="integration-with-sharepoint"></a>Intégration à SharePoint

Le tableau suivant répertorie les fonctionnalités prises en charge dans un déploiement hybride lors de l’intégration avec SharePoint.

||**SharePoint en local**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype entreprise Server 2015 en local** <br/> | Recherche de compétences <br/>  Présence dans SharePoint <br/> | Présence dans SharePoint <br/> |
|**Skype Entreprise Online** <br/> | Présence dans SharePoint <br/> | Présence dans SharePoint <br/> |


