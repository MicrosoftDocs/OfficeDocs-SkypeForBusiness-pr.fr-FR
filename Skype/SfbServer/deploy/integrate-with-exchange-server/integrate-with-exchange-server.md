---
title: Intégration de Skype entreprise Server à Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Résumé: passez en revue les étapes d’intégration d’Exchange Server 2016 ou Exchange Server 2013 et Skype entreprise Server.'
ms.openlocfilehash: 398ded1c138743c79de0e372b930dacef08fd94f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244042"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="214b4-103">Intégration de Skype entreprise Server à Exchange Server</span><span class="sxs-lookup"><span data-stu-id="214b4-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="214b4-104">**Résumé:** Passez en revue les étapes d’intégration d’Exchange Server 2013 ou version ultérieure et Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="214b4-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="214b4-105">Exchange Server 2013 ou version ultérieure, Skype entreprise Server est compatible et intégré.</span><span class="sxs-lookup"><span data-stu-id="214b4-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="214b4-106">Par exemple, les informations de présence d’un utilisateur de Skype entreprise peuvent être rapportées dans Microsoft Outlook. de même, Skype entreprise peut accéder au calendrier Outlook d’un utilisateur, noter qu’il dispose d’une réunion planifiée et montrer la présence de l’utilisateur en tant qu’il est occupé lors de la réunion.</span><span class="sxs-lookup"><span data-stu-id="214b4-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="214b4-107">Même si vous n’avez pas besoin d’exécuter Exchange Server pour pouvoir exécuter Skype entreprise Server (ou inversement), les deux produits renforcent l’utilisation de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="214b4-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="214b4-108">Cette documentation fournit des informations sur l’intégration de Skype entreprise Server et Exchange Server 2016 ou Exchange Server 2013, mais suppose la configuration initiale et la configuration de ces deux produits.</span><span class="sxs-lookup"><span data-stu-id="214b4-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="214b4-109">Pour plus d’informations sur le déploiement de Skype entreprise Server, voir le [Centre technique de Skype entreprise Server](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="214b4-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="214b4-110">Pour plus d’informations sur le déploiement d’Exchange Server, voir la documentation de déploiement pour votre version d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="214b4-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="214b4-111">Si vous intégrez une installation locale de Skype entreprise Server et Microsoft Exchange Online, voir Configurer l' [intégration entre Skype entreprise Server et Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="214b4-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="214b4-112">Si vous intégrez Skype entreprise Online à Exchange Server en local, reportez-vous à la rubrique [configuration OAuth de Skype entreprise Online et Exchange sur site](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="214b4-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="214b4-113">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="214b4-113">In this section</span></span>

[<span data-ttu-id="214b4-114">Configurer les applications partenaires dans Skype entreprise Server et Exchange Server</span><span class="sxs-lookup"><span data-stu-id="214b4-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="214b4-115">Configuration de Skype entreprise Server pour l’utilisation de l’archivage Exchange Server</span><span class="sxs-lookup"><span data-stu-id="214b4-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="214b4-116">Configurer SharePoint Server pour rechercher des données Skype Entreprise archivées</span><span class="sxs-lookup"><span data-stu-id="214b4-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="214b4-117">Configuration de Skype Entreprise Server pour utiliser le magasin de contacts unifié</span><span class="sxs-lookup"><span data-stu-id="214b4-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="214b4-118">Configurer l’utilisation de photos haute résolution dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="214b4-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="214b4-119">Configuration de la messagerie unifiée d’Exchange Server pour la messagerie vocale de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="214b4-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="214b4-120">Intégration de Skype entreprise Server et de Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="214b4-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="214b4-121">Configurer le magasin de contacts personnels sur les ordinateurs clients pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="214b4-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="214b4-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="214b4-122">See also</span></span>

[<span data-ttu-id="214b4-123">Planifier l’intégration de Skype Entreprise et d’Exchange</span><span class="sxs-lookup"><span data-stu-id="214b4-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
