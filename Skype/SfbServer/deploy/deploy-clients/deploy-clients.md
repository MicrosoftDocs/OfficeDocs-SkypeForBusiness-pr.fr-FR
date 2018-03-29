---
title: Déploiement des clients pour Skype Entreprise Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Résumé : Vue d’ensemble des méthodes d’installation de client entreprise pour Skype pour les entreprises.'
ms.openlocfilehash: d41ce5b2fe9b4717a9af78fb3072ae0da48b72ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a><span data-ttu-id="e5e5d-103">Déploiement des clients pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e5e5d-103">Deploy clients for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e5e5d-104">**Résumé :** Vue d’ensemble des méthodes d’installation de client entreprise pour Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="e5e5d-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="e5e5d-105">Comment déployer Skype pour entreprise à vos utilisateurs dépend de si vous avez acheté Skype pour les entreprises dans le cadre d’un plan d’Office 365, ou vous avez acheté une version sous licence de volume de Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="e5e5d-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="e5e5d-106">**Office 365** Si vous avez un plan Office 365 incluant Skype pour les entreprises, la technologie d’installation qui est utilisée est appelée Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="e5e5d-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="e5e5d-107">Avec Office 365, vous pouvez permettre à vos utilisateurs installer Skype pour entreprise pour eux-mêmes à partir du portail Office 365.</span><span class="sxs-lookup"><span data-stu-id="e5e5d-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="e5e5d-108">Ou bien, vous pouvez déployer Skype pour entreprise à vos utilisateurs en téléchargement du logiciel sur votre réseau local, puis à l’aide de vos outils de déploiement de logiciel existant, par exemple avec Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e5e5d-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="e5e5d-109">Pour plus d’informations d’installation sur Skype pour entreprise qui est fourni avec Office 365, voir [déployer le Skype pour client d’entreprise dans Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="e5e5d-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="e5e5d-110">**Licences en volume** Si vous avez une version de licence en volume de Skype pour les entreprises, la technologie d’installation qui est utilisée est Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="e5e5d-110">**Volume licensed** If you have a volume licensed version of Skype for Business, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="e5e5d-111">Un package d’installation Windows Installer se compose de plusieurs fichiers MSI.</span><span class="sxs-lookup"><span data-stu-id="e5e5d-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="e5e5d-112">Pour qu’un package MSI principal indépendant de la langue soit complet, il est accompagné d’un ou de plusieurs packages spécifiques à la langue.</span><span class="sxs-lookup"><span data-stu-id="e5e5d-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="e5e5d-113">Le programme d’installation assemble les packages individuels et effectue des tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e5e5d-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span>
    
<span data-ttu-id="e5e5d-114">Les rubriques de cette section décrivent comment utiliser et personnaliser le programme d’installation de Windows pour déployer le Skype pour client d’entreprise à vos utilisateurs par le biais de vos procédures habituelles.</span><span class="sxs-lookup"><span data-stu-id="e5e5d-114">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5e5d-115">En ligne complément de réunion pour Skype pour les entreprises, qui prend en charge la réunion de gestion depuis Outlook client de messagerie et de collaboration, installe automatiquement avec Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="e5e5d-115">The Online meeting Add-in for Skype for Business, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e5e5d-116">Le programme d’installation de Office 365 ne désinstalle pas les versions précédentes de Lync ou Communicator d’Office.</span><span class="sxs-lookup"><span data-stu-id="e5e5d-116">The Office 365 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="e5e5d-117">Le Skype pour client d’entreprise installe côte à côte avec d’autres clients Lync ou Communicator d’Office.</span><span class="sxs-lookup"><span data-stu-id="e5e5d-117">The Skype for Business client installs side-by-side with other Lync or Office Communicator clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="e5e5d-118">L’installation des clients Windows</span><span class="sxs-lookup"><span data-stu-id="e5e5d-118">Installing Windows clients</span></span>

- [<span data-ttu-id="e5e5d-119">Personnaliser l’installation du client Windows dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e5e5d-119">Customize Windows client installation in Skype for Business Server 2015</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="e5e5d-120">Configurer l’expérience client avec Skype pour entreprise</span><span class="sxs-lookup"><span data-stu-id="e5e5d-120">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="e5e5d-121">Configurer la liste de contacts Smart dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="e5e5d-121">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="e5e5d-122">Installation de périphériques clients</span><span class="sxs-lookup"><span data-stu-id="e5e5d-122">Installing device clients</span></span>

- [<span data-ttu-id="e5e5d-123">Installation et test Skype pour Business pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="e5e5d-123">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="e5e5d-124">Installation et test Skype pour entreprise pour iOS</span><span class="sxs-lookup"><span data-stu-id="e5e5d-124">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="e5e5d-125">Déployer un système de salle de Skype dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="e5e5d-125">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="e5e5d-126">Déployer Skype salle systèmes v2</span><span class="sxs-lookup"><span data-stu-id="e5e5d-126">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="e5e5d-127">Déploiement de la VDI Lync plug-in avec Skype Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e5e5d-127">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="e5e5d-128">Déployer des clients Web téléchargeables Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e5e5d-128">Deploy Web downloadable clients in Skype for Business Server 2015</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="e5e5d-129">Personnaliser l’expérience de client Mac dans Skype pour entreprise</span><span class="sxs-lookup"><span data-stu-id="e5e5d-129">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="e5e5d-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e5e5d-130">See also</span></span>

#### 

[<span data-ttu-id="e5e5d-131">Déployer le Skype pour client d’entreprise pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="e5e5d-131">Deploy the Skype for Business client for your organization</span></span>](https://support.officeppe.com/en-us/article/Deploy-the-Skype-for-Business-client-for-your-organization-8c563b81-22c9-4024-9efe-9fe28c7bbc96?ui=en-US&amp;rs=en-US&amp;ad=US)

