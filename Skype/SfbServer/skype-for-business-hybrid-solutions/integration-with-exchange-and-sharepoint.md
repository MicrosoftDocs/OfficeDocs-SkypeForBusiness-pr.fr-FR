---
title: Intégration avec Exchange et Microsoft Office SharePoint Online
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
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
description: 'Résumé : Découvrez l’intégration de Skype Entreprise Server 2015 avec Exchange et SharePoint.'
ms.openlocfilehash: 943392fbd63238621825edad380ac9c140935635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821104"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Intégration avec Exchange et Microsoft Office SharePoint Online

**Résumé :** Découvrez l’intégration de Skype Entreprise Server 2015 avec Exchange et SharePoint.

Vous pouvez configurer des déploiements Skype Entreprise Server 2015 pour l’intégration à Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 et SharePoint Server, à la fois en local et en ligne. Sauf indication contraire, les fonctionnalités répertoriées dans le tableau suivant sont pris en charge avec tous les clients. Pour plus d’informations sur la prise en charge des clients, voir comparaison des fonctionnalités client de bureau pour les tableaux de comparaison des clients [Skype](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) Entreprise et Skype Entreprise Online dans [clients pour Skype Entreprise Online.](https://go.microsoft.com/fwlink/p/?LinkId=281902)

## <a name="integration-with-exchange-server"></a>Intégration à Exchange Server

Les tableaux suivants listent les fonctionnalités prise en charge dans un déploiement hybride lorsqu’elles sont intégrées Microsoft Exchange Server.

 **Skype Entreprise Server sur site et Exchange en local**


|**Fonctionnalité**|**Notes**|
|:-----|:-----|
|Messagerie instantanée/présence dans Outlook  <br/> |Pour plus d’informations, [consultez la messagerie instantanée et la présence.](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)  <br/> |
|Planifier et participer à une réunion en ligne via Outlook  <br/> |Pour plus d’informations, voir [Integrate Skype for Business Server 2015 with Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Messagerie instantanée/présence dans Outlook Web App  <br/> |Pour plus d’informations, [voir Configure a hybrid environment in Skype for Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Planifier et participer à une réunion en ligne via Outlook Web App  <br/> ||
|Messagerie instantanée/présence dans les clients mobiles  <br/> ||
|Participer à des réunions en ligne dans des clients mobiles  <br/> |Pour plus d’informations, voir [Deploying Mobility](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Publier l’état en fonction des informations de libre/occupé du calendrier Outlook  <br/> ||
|Liste des contacts (via le magasin de contacts unifié)  <br/> |Nécessite Exchange 2016 ou Exchange 2013.  <br/> Un client de bureau Lync 2013 ou Skype Entreprise est requis.  <br/>  Pour plus d’informations, [voir Configure Skype for Business Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Photo de contact haute résolution dans le client Lync 2013, le client Skype Entreprise et Lync Web App.  <br/> |Nécessite Exchange 2016 ou Exchange 2013.  <br/> Pour plus d’informations, [voir Configure the use of high-resolution photos in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Pour les photos sur l’application Skype Entreprise pour MAC et Mobile, l’intégration entre Skype Entreprise Server 2015 et Exchange Server doit être configurée comme décrit dans Configurer les applications partenaires dans [Skype Entreprise Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md)et Exchange Server . <br/> |
|Délégation de réunion  <br/> |Pris en charge uniquement lorsque les deux utilisateurs sont en ligne dans la même forêt, ou que les deux sont tous deux locaux. Pour plus d’informations, voir [solutions hybrides Skype Entreprise.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur  <br/> ||
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange  <br/> |Nécessite Exchange 2016 ou Exchange 2013.  <br/> Pour plus d’informations, [voir Deployment Checklist for Archiving](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Rechercher du contenu archivé  <br/> |Nécessite Exchange 2016 ou Exchange 2013.  <br/> |
|Messagerie vocale  <br/> |Pour plus d’informations, voir [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |

 **Skype Entreprise Server local et Exchange Online**


|**Fonctionnalité**|**Notes**|
|:-----|:-----|
|Messagerie instantanée/présence dans Outlook  <br/> |Pour plus d’informations, voir [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Planifier et participer à une réunion en ligne via Outlook  <br/> ||
|Messagerie instantanée/présence dans Outlook Web App  <br/> |Pour plus d’informations, voir [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Planifier et participer à une réunion en ligne à partir d’Outlook Web App  <br/> |Pour plus d’informations, voir [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Messagerie instantanée/présence dans les clients mobiles  <br/> ||
|Rejoindre une réunion en ligne dans des clients mobiles  <br/> ||
|Publier l’état en fonction des informations de libre/occupé du calendrier Outlook  <br/> ||
|Liste des contacts (via le magasin de contacts unifié).  <br/> |Lync Server 2013 uniquement. Un client de bureau Lync 2013 ou Skype Entreprise est requis.  <br/> Pour plus d’informations, voir [Configure Skype for Business Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Photo de contact haute résolution dans le client Lync 2013, le client Skype Entreprise et Lync Web App.  <br/> |Pour plus d’informations, [voir Configure the use of high-resolution photos in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Pour les photos sur l’application Skype Entreprise pour MAC et Mobile, l’intégration entre Skype Entreprise Server 2015 et Exchange Server doit être configurée comme décrit dans Configurer l’intégration entre Skype Entreprise Server local et [Outlook Web App.](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Délégation de réunion  <br/> |Pris en charge uniquement lorsque les deux utilisateurs sont en ligne dans la même forêt, ou que les deux sont tous deux locaux. Pour plus d’informations, voir [solutions hybrides Skype Entreprise.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur  <br/> ||
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange  <br/> |Pour plus d’informations, [voir Deployment Checklist for Archiving](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Rechercher du contenu archivé  <br/> |Pour plus d’informations, voir [l’adresse Configure Exchange for SharePoint eDiscovery Center](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Messagerie vocale  <br/> |Pour plus d’informations, voir [Providing Lync Server 2013 Users Voice Mail on Hosted Exchange UM](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Skype Entreprise Online et Exchange en local**


|**Fonctionnalité**|**Notes**|
|:-----|:-----|
|Présence dans Outlook  <br/> ||
|Répondre par messagerie instantanée, appel PSTN, appel Skype ou appel vidéo à partir d’un e-mail Outlook  <br/> ||
|Planifier et participer à des réunions en ligne via Outlook  <br/> ||
|Messagerie instantanée/présence dans les clients mobiles  <br/> ||
|Participer à des réunions en ligne dans des clients mobiles  <br/> ||
|Publier l’état en fonction des informations de libre/occupé du calendrier Outlook  <br/> ||
|L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur  <br/> ||
|Photo de contact haute résolution dans le client Lync 2013 ou Skype Entreprise.  <br/> |Nécessite Exchange 2016 ou Exchange 2013. Cela n’est pas pris en charge dans Lync Web App lorsque les utilisateurs sont homed sur Skype Entreprise Online.  <br/> |
|Délégation de réunion  <br/> |Pris en charge uniquement lorsque les deux utilisateurs sont en ligne dans la même forêt, ou que les deux sont tous deux locaux. Pour plus d’informations, voir [solutions hybrides Skype Entreprise.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur  <br/> ||
|Historique des conversations côté serveur  <br/> ||

 **Skype Entreprise Online et Exchange Online**


|**Fonctionnalité**|**Notes**|
|:-----|:-----|
|Messagerie instantanée/présence dans Outlook  <br/> ||
|Planifier et participer à des réunions en ligne via Outlook  <br/> ||
|Messagerie instantanée/présence dans Outlook Web App  <br/> ||
|Planifier et participer à une réunion en ligne à partir d’Outlook Web App  <br/> ||
|Messagerie instantanée/présence dans les clients mobiles  <br/> ||
|Rejoindre une réunion en ligne dans des clients mobiles  <br/> ||
|Publier l’état en fonction des informations de libre/occupé du calendrier Outlook  <br/> ||
|L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur  <br/> ||
|Liste des contacts (via le magasin de contacts unifié)  <br/> |Client Lync Server 2013 ou Skype Entreprise requis  <br/> |
|Photo de contact haute résolution dans Lync 2013, le client Skype Entreprise et Lync Web App  <br/> ||
|Délégation de réunion  <br/> |Pris en charge uniquement lorsque les deux utilisateurs sont en ligne dans la même forêt, ou que les deux sont tous deux locaux. Pour plus d’informations, voir [solutions hybrides Skype Entreprise.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange  <br/> ||
|Rechercher du contenu archivé  <br/> ||
|Messagerie vocale  <br/> ||

## <a name="integration-with-sharepoint"></a>Intégration à SharePoint

Le tableau suivant répertorie les fonctionnalités prise en charge dans un déploiement hybride lorsqu’elle est intégrée à SharePoint.

||**SharePoint en local**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype Entreprise Server 2015 local** <br/> | Recherche de compétences <br/>  Présence dans SharePoint <br/> | Présence dans SharePoint <br/> |
|**Skype Entreprise Online** <br/> | Présence dans SharePoint <br/> | Présence dans SharePoint <br/> |


