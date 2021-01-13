---
title: Déployer des clients pour Skype Entreprise Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Résumé : Vue d’ensemble des méthodes d’installation du client d’entreprise pour Skype Entreprise.'
ms.openlocfilehash: ccaed5620c7f524a5a39fc6a35e6d688cd97a0eb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805694"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="16685-103">Déployer des clients pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="16685-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="16685-104">**Résumé :** Vue d’ensemble des méthodes d’installation des clients d’entreprise pour Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="16685-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="16685-105">La façon dont vous déployez Skype Entreprise pour vos utilisateurs varie selon que vous avez acheté Skype Entreprise dans le cadre d’une offre Microsoft 365 ou Office 365 ou que vous avez acheté une version avec licence en volume de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="16685-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of a Microsoft 365 or Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="16685-106">**Microsoft 365 ou Office 365** Si vous avez un plan Microsoft 365 ou Office 365 qui inclut Skype Entreprise, la technologie d’installation utilisée est appelée « Click-to-Run ».</span><span class="sxs-lookup"><span data-stu-id="16685-106">**Microsoft 365 or Office 365** If you have a Microsoft 365 or Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="16685-107">Vous pouvez laisser vos utilisateurs installer Skype Entreprise eux-mêmes à partir du Centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="16685-107">You can let your users install Skype for Business for themselves from the Microsoft 365 admin center.</span></span> <span data-ttu-id="16685-108">Vous pouvez également déployer Skype Entreprise pour vos utilisateurs en téléchargeant le logiciel sur votre réseau local, puis en utilisant vos outils de déploiement de logiciels existants, par exemple avec Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="16685-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="16685-109">Pour plus d’informations sur l’installation de Skype Entreprise avec Microsoft 365 et Office 365, voir Déployer le client Skype Entreprise dans [Microsoft 365 ou Office 365.](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)</span><span class="sxs-lookup"><span data-stu-id="16685-109">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="16685-110">**Licence en volume** Si vous avez une version avec licence en volume du client Skype Entreprise 2015 ou 2016, la technologie d’installation utilisée est Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="16685-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="16685-111">Un package d’installation basé sur Windows Installer se compose de plusieurs fichiers MSI.</span><span class="sxs-lookup"><span data-stu-id="16685-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="16685-112">Un package MSI principal indépendant de la langue s’accompagne d’un ou plusieurs packages spécifiques à la langue pour en faire un produit complet.</span><span class="sxs-lookup"><span data-stu-id="16685-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="16685-113">Le programme d’installation assemble les packages individuels et effectue des tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="16685-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="16685-114">Le client Skype Entreprise 2019 utilise des programme d’installation « En un clic ».</span><span class="sxs-lookup"><span data-stu-id="16685-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="16685-115">Les rubriques de cette section décrivent comment utiliser et personnaliser Windows Installer pour déployer le client Skype Entreprise pour vos utilisateurs au cours de vos procédures normales.</span><span class="sxs-lookup"><span data-stu-id="16685-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="16685-116">Le add-in de réunion Skype pour Microsoft Office, qui prend en charge la gestion des réunions à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec les clients Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="16685-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="16685-117">Les programmes d’installation de Microsoft 365 et Office 365 ne désinstallent pas les versions précédentes de Lync.</span><span class="sxs-lookup"><span data-stu-id="16685-117">The Microsoft 365 and Office 365 setup programs don't uninstall previous versions of Lync.</span></span> <span data-ttu-id="16685-118">Le client Skype Entreprise s’installe côte à côte avec d’autres clients Lync.</span><span class="sxs-lookup"><span data-stu-id="16685-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="16685-119">Installation des clients Windows</span><span class="sxs-lookup"><span data-stu-id="16685-119">Installing Windows clients</span></span>

- [<span data-ttu-id="16685-120">Personnaliser l’installation du client Windows dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="16685-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="16685-121">Configurer l’expérience client avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="16685-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="16685-122">Configurer la liste de contacts intelligents dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="16685-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="16685-123">Installation des clients d’appareil</span><span class="sxs-lookup"><span data-stu-id="16685-123">Installing device clients</span></span>

- [<span data-ttu-id="16685-124">Installer et tester Skype Entreprise pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="16685-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="16685-125">Installer et tester Skype Entreprise pour iOS</span><span class="sxs-lookup"><span data-stu-id="16685-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="16685-126">Déployer le plug-in Lync VDI avec Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="16685-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="16685-127">Déployer des clients web téléchargeables dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="16685-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="16685-128">Personnaliser l’expérience client Mac dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="16685-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="16685-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16685-129">See also</span></span>

[<span data-ttu-id="16685-130">Déployer le client Skype Entreprise dans Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="16685-130">Deploy the Skype for Business client in Microsoft 365 or Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
