---
title: Intégration avec Exchange et Microsoft Office SharePoint Online
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 'Résumé : Découvrez l’intégration Skype Entreprise Server 2015 avec Exchange et SharePoint.'
ms.openlocfilehash: 6805296716970df896a42a3e01a89eb212930ecb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746510"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Intégration avec Exchange et Microsoft Office SharePoint Online

**Résumé :** Découvrez comment Skype Entreprise Server 2015 avec Exchange et SharePoint.

Vous pouvez configurer des déploiements Skype Entreprise Server 2015 pour l’intégration à Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 et SharePoint Server, à la fois en local et en ligne. Sauf indication contraire, les fonctionnalités répertoriées dans le tableau suivant sont pris en charge avec tous les clients. Pour plus d’informations sur la prise en charge des clients, voir comparaison des fonctionnalités client de bureau pour les tableaux de comparaison des clients [Skype Entreprise](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) et Skype Entreprise Online dans [Clients for Skype Entreprise Online](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

## <a name="integration-with-exchange-server"></a>Intégration à Exchange Server

Les tableaux suivants listent les fonctionnalités prise en charge dans un déploiement hybride lorsqu’elles sont intégrées à Microsoft Exchange Server.

 **Skype Entreprise Server local et Exchange local**


|**Fonctionnalité**|**Notes**|
|:-----|:-----|
|Messagerie instantanée/présence dans Outlook  <br/> |Pour plus d’informations, [consultez la messagerie instantanée et la présence.](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence)  <br/> |
|Planifier et participer à une réunion en ligne via Outlook  <br/> |Pour plus d’informations, [voir Intégrer Skype Entreprise Server 2015 avec Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Messagerie instantanée/présence dans Outlook Web App  <br/> |Pour plus d’informations, [voir Configure a hybrid environment in Skype Entreprise Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Planifier et participer à une réunion en ligne via Outlook Web App  <br/> ||
|Messagerie instantanée/présence dans les clients mobiles  <br/> ||
|Participer à des réunions en ligne dans des clients mobiles  <br/> |Pour plus d’informations, voir [Deploying Mobility](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility).  <br/> |
|Publier l’état en fonction Outlook informations de libre/occupé du calendrier  <br/> ||
|Liste des contacts (via le magasin de contacts unifié)  <br/> |Nécessite Exchange 2016 ou Exchange 2013.  <br/> Un client de bureau Lync 2013 ou Skype Entreprise de bureau est requis.  <br/>  Pour plus d’informations, [voir Configure Skype Entreprise Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Photo de contact haute résolution dans le client Lync 2013, Skype Entreprise client et Lync Web App.  <br/> |Nécessite Exchange 2016 ou Exchange 2013.  <br/> Pour plus d’informations, [voir Configure the use of high-resolution photos in Skype Entreprise Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Pour les photos sur l’application Skype Entreprise pour MAC et Mobile, l’intégration entre Skype Entreprise Server 2015 et Exchange Server doit être configurée comme décrit dans Configurer les applications partenaires dans [Skype Entreprise Server et Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md). <br/> |
|Délégation de réunion  <br/> |Pris en charge uniquement lorsque les deux utilisateurs sont en ligne dans la même forêt, ou que les deux sont tous deux locaux. Pour plus d’informations, voir Configurer la connectivité hybride [entre Skype Entreprise Server et Teams](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md). <br/> |
|L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur  <br/> ||
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange  <br/> |Nécessite Exchange 2016 ou Exchange 2013.  <br/> Pour plus d’informations, [voir Deployment Checklist for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving).  <br/> |
|Rechercher du contenu archivé  <br/> |Nécessite Exchange 2016 ou Exchange 2013.  <br/> |
|Messagerie vocale  <br/> |Pour plus d’informations, voir [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail).  <br/> |

 **Skype Entreprise Server sur site et Exchange Online**


|**Fonctionnalité**|**Notes**|
|:-----|:-----|
|Messagerie instantanée/présence dans Outlook  <br/> |Pour plus d’informations, voir [Configure integration between on-premises Skype Entreprise Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Planifier et participer à une réunion en ligne via Outlook  <br/> ||
|Messagerie instantanée/présence dans Outlook Web App  <br/> |Pour plus d’informations, voir [Configure integration between on-premises Skype Entreprise Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Planifier et participer à une réunion en ligne à partir Outlook Web App  <br/> |Pour plus d’informations, voir [Configure integration between on-premises Skype Entreprise Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Messagerie instantanée/présence dans les clients mobiles  <br/> ||
|Rejoindre une réunion en ligne dans des clients mobiles  <br/> ||
|Publier l’état en fonction Outlook informations de libre/occupé du calendrier  <br/> ||
|Liste des contacts (via le magasin de contacts unifié).  <br/> |Lync Server 2013 uniquement. Un client de bureau Lync 2013 ou Skype Entreprise de bureau est requis.  <br/> Pour plus d’informations, [voir Configure Skype Entreprise Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Photo de contact haute résolution dans le client Lync 2013, Skype Entreprise client et Lync Web App.  <br/> |Pour plus d’informations, [voir Configure the use of high-resolution photos in Skype Entreprise Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Pour les photos sur l’application Skype Entreprise pour MAC et Mobile, l’intégration entre Skype Entreprise Server 2015 et Exchange Server doit être configurée comme décrit dans Configurer l’intégration entre Skype Entreprise Server local et [Outlook Web App.](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Délégation de réunion  <br/> |Pris en charge uniquement lorsque les deux utilisateurs sont en ligne dans la même forêt, ou que les deux sont tous deux locaux. Pour plus d’informations, [voir Skype Entreprise solutions hybrides.](/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange’utilisateur  <br/> ||
|Archivage de contenu (messagerie instantanée et réunion) dans Exchange  <br/> |Pour plus d’informations, [voir Deployment Checklist for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving).  <br/> |
|Rechercher du contenu archivé  <br/> |Pour plus d’informations, consultez la [Exchange configurer SharePoint centre eDiscovery](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|Messagerie vocale  <br/> |Pour plus d’informations, voir [Providing Lync Server 2013 Users Voice Mail on Hosted Exchange UM](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um).  <br/> |


## <a name="integration-with-sharepoint"></a>Intégration à SharePoint

Le tableau suivant répertorie les fonctionnalités prise en charge dans un déploiement hybride lorsqu’elle est intégrée à SharePoint.

||**SharePoint en local**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype Entreprise Server 2015 en local** <br/> | Recherche de compétences <br/>  Présence dans SharePoint <br/> | Présence dans SharePoint <br/> |
|**Skype Entreprise Online** <br/> | Présence dans SharePoint <br/> | Présence dans SharePoint <br/> |
