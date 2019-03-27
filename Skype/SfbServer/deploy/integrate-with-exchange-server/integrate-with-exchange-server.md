---
title: Intégrer Skype pour Business Server avec Exchange Server
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
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Résumé : Passez en revue les étapes d’intégration pour Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server.'
ms.openlocfilehash: d08bf95894febb224e88cc1c40dce1f693b99704
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873533"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="4c4cd-103">Intégrer Skype pour Business Server avec Exchange Server</span><span class="sxs-lookup"><span data-stu-id="4c4cd-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="4c4cd-104">**Résumé :** Passez en revue les étapes d’intégration pour Exchange Server 2013 ou version ultérieure et Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="4c4cd-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="4c4cd-105">Exchange Server 2013 ou version ultérieure et Skype pour Business Server sont compatibles et intègrent.</span><span class="sxs-lookup"><span data-stu-id="4c4cd-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="4c4cd-106">Par exemple, Skype des informations de présence utilisateur entreprise peut être signalé dans Microsoft Outlook ; de même, Skype pour les entreprises permettre accéder calendrier d’Outlook d’un utilisateur, notez que l’utilisateur a une réunion est prévue et afficher la présence de l’utilisateur en tant qu’occupé (e) pendant la réunion.</span><span class="sxs-lookup"><span data-stu-id="4c4cd-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="4c4cd-107">Bien que vous n’êtes pas obligé d’exécuter Exchange Server pour pouvoir exécuter Skype pour Business Server (ou vice versa) ensemble les deux produits améliorer l’expérience utilisateur de l’autre.</span><span class="sxs-lookup"><span data-stu-id="4c4cd-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="4c4cd-108">Cette documentation fournit des informations sur l’intégration de Skype pour Business Server et Exchange Server 2016 ou Exchange Server 2013, mais il suppose que l’installation initiale et la configuration de ces deux produits a déjà eu lieu.</span><span class="sxs-lookup"><span data-stu-id="4c4cd-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="4c4cd-109">Pour plus d’informations sur le déploiement Skype pour Business Server, consultez le [Skype pour Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="4c4cd-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="4c4cd-110">Pour plus d’informations sur le déploiement d’Exchange Server, consultez la documentation de déploiement pour votre version d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="4c4cd-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="4c4cd-111">Si vous intégrez une installation sur site Skype pour Business Server avec Microsoft Exchange Online, voir [configurer l’intégration entre locale Skype pour Business Server et Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="4c4cd-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="4c4cd-112">Si vous intégrez Skype pour Business Online avec Exchange Server sur site, voir [Configurer les OAuth entre Skype pour Business Online et Exchange sur site](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="4c4cd-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4c4cd-113">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="4c4cd-113">In this section</span></span>

[<span data-ttu-id="4c4cd-114">Configurer des applications partenaires Skype pour Business Server et Exchange Server</span><span class="sxs-lookup"><span data-stu-id="4c4cd-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="4c4cd-115">Configurer Skype pour Business Server utilisant l’archivage d’Exchange Server</span><span class="sxs-lookup"><span data-stu-id="4c4cd-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="4c4cd-116">Configurer SharePoint Server pour rechercher des données Skype Entreprise archivées</span><span class="sxs-lookup"><span data-stu-id="4c4cd-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="4c4cd-117">Configuration de Skype Entreprise Server pour utiliser le magasin de contacts unifié</span><span class="sxs-lookup"><span data-stu-id="4c4cd-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="4c4cd-118">Configurer l’utilisation de photos haute résolution dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4c4cd-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="4c4cd-119">Configuration de la messagerie unifiée d’Exchange Server pour la messagerie vocale de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4c4cd-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="4c4cd-120">Intégration de Skype pour Business Server et Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="4c4cd-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="4c4cd-121">Configurer le magasin de contacts personnels sur les ordinateurs clients pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4c4cd-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="4c4cd-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c4cd-122">See also</span></span>

[<span data-ttu-id="4c4cd-123">Planifier l’intégration de Skype Entreprise et d’Exchange</span><span class="sxs-lookup"><span data-stu-id="4c4cd-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
