---
title: Intégrer Skype Entreprise Server à Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Résumé : Examinez les étapes d’intégration pour Exchange Server 2016 ou Exchange Server 2013 et Skype Entreprise Server.'
ms.openlocfilehash: b19aa73e62b12674551690b716144fb67b4cd715
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104850"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="bb8d1-103">Intégrer Skype Entreprise Server à Exchange Server</span><span class="sxs-lookup"><span data-stu-id="bb8d1-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="bb8d1-104">**Résumé :** Passer en revue les étapes d’intégration Exchange Server 2013 ou ultérieur et Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="bb8d1-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="bb8d1-105">Exchange Server 2013 ou ultérieure et Skype Entreprise Server sont compatibles et s’intègrent bien.</span><span class="sxs-lookup"><span data-stu-id="bb8d1-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="bb8d1-106">Par exemple, les informations de présence des utilisateurs de Skype Entreprise peuvent être signalées dans Microsoft Outlook . De même, Skype Entreprise peut accéder au calendrier Outlook d’un utilisateur, noter qu’une réunion est prévue pour l’utilisateur et afficher la présence de l’utilisateur comme occupé pendant la réunion.</span><span class="sxs-lookup"><span data-stu-id="bb8d1-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="bb8d1-107">Bien que vous n’avez pas besoin d’exécuter Exchange Server pour exécuter Skype Entreprise Server (ou vice versa), les deux produits améliorent l’expérience utilisateur l’un de l’autre.</span><span class="sxs-lookup"><span data-stu-id="bb8d1-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="bb8d1-108">Cette documentation fournit des informations sur l’intégration de Skype Entreprise Server et Exchange Server 2016 ou Exchange Server 2013, mais elle suppose que la configuration initiale de ces deux produits a déjà eu lieu.</span><span class="sxs-lookup"><span data-stu-id="bb8d1-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="bb8d1-109">Pour plus d’informations sur le déploiement de Skype Entreprise Server, voir le [Tech Center Skype Entreprise Server.](../../../Hub/index.yml)</span><span class="sxs-lookup"><span data-stu-id="bb8d1-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](../../../Hub/index.yml).</span></span> <span data-ttu-id="bb8d1-110">Pour plus d’informations sur le déploiement Exchange Server consultez la documentation de déploiement de votre version d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="bb8d1-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="bb8d1-111">Si vous intégrez une installation locale de Skype Entreprise Server à Microsoft Exchange Online, voir Configurer l’intégration entre Skype Entreprise Server local et [Outlook Web App.](outlook-web-app.md)</span><span class="sxs-lookup"><span data-stu-id="bb8d1-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="bb8d1-112">Si vous intégrez Skype Entreprise Online à Exchange Server local, voir [Configurer OAuth](oauth-with-online-and-on-premises.md)entre Skype Entreprise Online et Exchange en local.</span><span class="sxs-lookup"><span data-stu-id="bb8d1-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bb8d1-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="bb8d1-113">In this section</span></span>

[<span data-ttu-id="bb8d1-114">Configurer des applications partenaires dans Skype Entreprise Server et Exchange Server</span><span class="sxs-lookup"><span data-stu-id="bb8d1-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="bb8d1-115">Configurer Skype Entreprise Server pour utiliser l’archivage Exchange Server entreprise</span><span class="sxs-lookup"><span data-stu-id="bb8d1-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="bb8d1-116">Configurer SharePoint Server pour rechercher des données Skype Entreprise archivées</span><span class="sxs-lookup"><span data-stu-id="bb8d1-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="bb8d1-117">Configurer Skype Entreprise Server pour utiliser le magasin de contacts unifié</span><span class="sxs-lookup"><span data-stu-id="bb8d1-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="bb8d1-118">Configurer l’utilisation de photos haute résolution dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bb8d1-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="bb8d1-119">Configurer Exchange Server messagerie unifiée pour la messagerie vocale Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bb8d1-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

<span data-ttu-id="bb8d1-120">[Intégration de Skype Entreprise Server et Microsoft Outlook Web App 2013](/previous-versions/office/communications/jj688055(v=ocs.16))</span><span class="sxs-lookup"><span data-stu-id="bb8d1-120">[Integrating Skype for Business Server and Microsoft Outlook Web App 2013](/previous-versions/office/communications/jj688055(v=ocs.16))</span></span>

[<span data-ttu-id="bb8d1-121">Configurer le magasin de contacts personnels sur les ordinateurs clients pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bb8d1-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="bb8d1-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb8d1-122">See also</span></span>

[<span data-ttu-id="bb8d1-123">Planifier l’intégration de Skype Entreprise et d’Exchange</span><span class="sxs-lookup"><span data-stu-id="bb8d1-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)