---
title: Déployer des clients pour Skype entreprise Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Résumé : vue d’ensemble des méthodes d’installation des clients d’entreprise pour Skype entreprise.'
ms.openlocfilehash: cdee3db6dc6fcec646ee2e15b6aeebc298d75b67
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778280"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="3d265-103">Déployer des clients pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="3d265-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="3d265-104">**Résumé :** Vue d’ensemble des méthodes d’installation des clients d’entreprise pour Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="3d265-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="3d265-105">Le mode de déploiement de Skype entreprise pour vos utilisateurs dépend de si vous avez acheté Skype entreprise dans le cadre d’un plan Office 365 ou si vous avez acheté une version avec licence en volume de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="3d265-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="3d265-106">**Office 365** Si vous disposez d’un plan Office 365 incluant Skype entreprise, la technologie d’installation utilisée est appelée « démarrer en un clic ».</span><span class="sxs-lookup"><span data-stu-id="3d265-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="3d265-107">Avec Office 365, vous pouvez permettre à vos utilisateurs d’installer Skype entreprise pour eux-mêmes à partir du centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d265-107">With Office 365, you can let your users install Skype for Business for themselves from the Microsoft 365 admin center.</span></span> <span data-ttu-id="3d265-108">Vous pouvez aussi déployer Skype entreprise auprès de vos utilisateurs en téléchargeant le logiciel sur votre réseau local, puis en utilisant vos outils de déploiement de logiciels existants, tels que le gestionnaire de configuration de point de terminaison Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d265-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="3d265-109">Pour plus d’informations sur l’installation de Skype entreprise qui est fournie avec Office 365, voir [Deploy the Skype for Business client in office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="3d265-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="3d265-110">**Licence en volume** Si vous disposez d’une version sous licence en volume du client Skype entreprise 2015 ou 2016, la technologie d’installation utilisée est Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="3d265-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="3d265-111">Un package d’installation basé sur Windows Installer se compose de plusieurs fichiers MSI.</span><span class="sxs-lookup"><span data-stu-id="3d265-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="3d265-112">Un package MSI principal indépendant de la langue s’accompagne d’un ou plusieurs packages spécifiques à la langue pour en faire un produit complet.</span><span class="sxs-lookup"><span data-stu-id="3d265-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="3d265-113">Le programme d’installation assemble les packages individuels et effectue des tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3d265-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="3d265-114">Le client Skype entreprise 2019 utilise des programmes d’installation « démarrer en un clic ».</span><span class="sxs-lookup"><span data-stu-id="3d265-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="3d265-115">Les rubriques de cette section décrivent comment utiliser et personnaliser Windows Installer pour déployer le client Skype entreprise pour vos utilisateurs par le biais de vos procédures normales.</span><span class="sxs-lookup"><span data-stu-id="3d265-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d265-116">Le complément réunion Skype pour Microsoft Office, qui prend en charge la gestion des réunions à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec les clients Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="3d265-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3d265-117">Le programme d’installation d’Office 365 ne désinstalle pas les versions précédentes de Lync.</span><span class="sxs-lookup"><span data-stu-id="3d265-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="3d265-118">Le client Skype entreprise s’installe côte à côte avec d’autres clients Lync.</span><span class="sxs-lookup"><span data-stu-id="3d265-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="3d265-119">Installation des clients Windows</span><span class="sxs-lookup"><span data-stu-id="3d265-119">Installing Windows clients</span></span>

- [<span data-ttu-id="3d265-120">Personnaliser l’installation du client Windows dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="3d265-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="3d265-121">Configuration de l’expérience client avec Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="3d265-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="3d265-122">Configurer la liste de contacts dynamiques dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="3d265-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="3d265-123">Installation de clients d’appareils</span><span class="sxs-lookup"><span data-stu-id="3d265-123">Installing device clients</span></span>

- [<span data-ttu-id="3d265-124">Installer et tester Skype entreprise pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="3d265-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="3d265-125">Installation et test de Skype entreprise pour iOS</span><span class="sxs-lookup"><span data-stu-id="3d265-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="3d265-126">Déployer le plug-in Lync VDI avec Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="3d265-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="3d265-127">Déploiement de clients Web téléchargeables dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="3d265-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="3d265-128">Personnaliser l’expérience client Mac dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="3d265-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="3d265-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d265-129">See also</span></span>

[<span data-ttu-id="3d265-130">Déployer le client Skype entreprise dans Office 365</span><span class="sxs-lookup"><span data-stu-id="3d265-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
