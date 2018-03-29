---
title: Intégration de Skype Entreprise Server 2015 à Exchange Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Résumé : Passez en revue les étapes d’intégration de 2016 d’Exchange Server ou Exchange Server 2013 et Skype pour Business Server 2015.'
ms.openlocfilehash: c8cbecd6b78e3dc14ad2133a93d9fc2d1f6bb3d6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="integrate-skype-for-business-server-2015-with-exchange-server"></a><span data-ttu-id="dca6c-103">Intégration de Skype Entreprise Server 2015 à Exchange Server</span><span class="sxs-lookup"><span data-stu-id="dca6c-103">Integrate Skype for Business Server 2015 with Exchange Server</span></span>
 
<span data-ttu-id="dca6c-104">**Résumé :** Passez en revue les étapes d’intégration de 2016 d’Exchange Server ou Exchange Server 2013 et Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dca6c-104">**Summary:** Review integration steps for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="dca6c-105">2016 d’Exchange Server ou Exchange Server 2013 et Skype pour Business Server 2015 sont compatibles et s’intègrent parfaitement.</span><span class="sxs-lookup"><span data-stu-id="dca6c-105">Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015 are compatible and integrate well.</span></span> <span data-ttu-id="dca6c-106">Par exemple, Skype pour les informations de présence des utilisateurs professionnels peut être signalée dans Microsoft Outlook ; de la même manière, Skype pour entreprise peut accéder le calendrier d’Outlook d’un utilisateur, notez que l’utilisateur a une réunion prévue et afficher la présence de l’utilisateur en tant qu’occupé (e) au cours de la réunion.</span><span class="sxs-lookup"><span data-stu-id="dca6c-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="dca6c-107">Bien que vous n’avez pas à l’exécution d’Exchange Server pour s’exécuter Skype pour Business Server (ou vice versa) les deux produits ensemble améliorer l’autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dca6c-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>
  
<span data-ttu-id="dca6c-108">Cette documentation fournit des informations sur l’intégration de Skype pour Business Server 2015 et 2016 d’Exchange Server ou Exchange Server 2013 de, mais elle suppose l’installation initiale et la configuration de ces deux produits s’est déjà produit.</span><span class="sxs-lookup"><span data-stu-id="dca6c-108">This documentation provides information on integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="dca6c-109">Pour plus d’informations sur le déploiement de Skype pour Business Server 2015 voir le [Skype pour Business Server 2015 Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="dca6c-109">For details about deploying Skype for Business Server 2015 see the [Skype for Business Server 2015 Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="dca6c-110">Pour plus d’informations sur le déploiement d’Exchange Server, consultez la documentation sur le déploiement de votre version de Exchange.</span><span class="sxs-lookup"><span data-stu-id="dca6c-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>
  
<span data-ttu-id="dca6c-111">Si vous intégrez une installation locale sur de Skype pour 2015 de serveur d’entreprise avec Microsoft Exchange Online, consultez [configurer l’intégration entre Skype sur site pour Business Server 2015 et Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="dca6c-111">If you are integrating an on premises installation of Skype for Business Server 2015 with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](outlook-web-app.md).</span></span>
  
<span data-ttu-id="dca6c-112">Si vous intégrez Skype pour entreprise en ligne avec Exchange Server dans les locaux, consultez [Configurer les OAuth entre Skype pour Business Online et Exchange sur site](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="dca6c-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="dca6c-113">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="dca6c-113">In this section</span></span>

[<span data-ttu-id="dca6c-114">Configurer des applications partenaires dans Skype pour Business Server 2015 et Exchange Server</span><span class="sxs-lookup"><span data-stu-id="dca6c-114">Configure partner applications in Skype for Business Server 2015 and Exchange Server</span></span>](configure-partner-applications.md)
  
[<span data-ttu-id="dca6c-115">Configurer Skype pour 2015 de serveur d’entreprise à utiliser Exchange Server d’archivage</span><span class="sxs-lookup"><span data-stu-id="dca6c-115">Configure Skype for Business Server 2015 to use Exchange Server archiving</span></span>](use-exchange-archiving.md)
  
[<span data-ttu-id="dca6c-116">Configuration de SharePoint Server pour rechercher Skype archivé pour les données de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="dca6c-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)
  
[<span data-ttu-id="dca6c-117">Configurer Skype pour 2015 de serveur d’entreprise à utiliser le magasin de contacts unifié</span><span class="sxs-lookup"><span data-stu-id="dca6c-117">Configure Skype for Business Server 2015 to use the unified contact store</span></span>](use-the-unified-contact-store.md)
  
[<span data-ttu-id="dca6c-118">Configurer l’utilisation de photos haute résolution dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dca6c-118">Configure the use of high-resolution photos in Skype for Business Server 2015</span></span>](high-resolution-photos.md)
  
[<span data-ttu-id="dca6c-119">Configurer Exchange Server la messagerie unifiée pour Skype pour la messagerie vocale Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dca6c-119">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)
  
[<span data-ttu-id="dca6c-120">Intégration de Skype pour Business Server 2015 et Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="dca6c-120">Integrating Skype for Business Server 2015 and Microsoft Outlook Web App 2013</span></span>](http://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)
  
[<span data-ttu-id="dca6c-121">Configurer le magasin de contacts personnels sur les ordinateurs clients pour Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dca6c-121">Configure the personal contacts store on client computers for Skype for Business Server 2015</span></span>](personal-contacts-store.md)
  
## <a name="see-also"></a><span data-ttu-id="dca6c-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dca6c-122">See also</span></span>

#### 

[<span data-ttu-id="dca6c-123">Planifier l’intégration de Skype pour les entreprises et Exchange</span><span class="sxs-lookup"><span data-stu-id="dca6c-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)

