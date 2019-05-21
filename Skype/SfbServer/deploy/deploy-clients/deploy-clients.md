---
title: Déploiement de clients pour Skype entreprise Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Résumé: vue d’ensemble des méthodes d’installation du client d’entreprise pour Skype entreprise.'
ms.openlocfilehash: df9ac5356c05001df09168ca619ffc200b35ea4f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282443"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="ebdd2-103">Déploiement de clients pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ebdd2-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="ebdd2-104">**Résumé:** Vue d’ensemble des méthodes d’installation du client d’entreprise pour Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="ebdd2-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="ebdd2-105">Le mode de déploiement de Skype entreprise pour vos utilisateurs dépend de la manière dont vous avez acheté Skype entreprise dans le cadre d’une offre Office 365 ou si vous avez acheté une version sous licence en volume de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="ebdd2-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="ebdd2-106">**Office 365** Si vous avez un plan Office 365 incluant Skype entreprise, la technologie d’installation qui est utilisée est appelée démarrer en un clic.</span><span class="sxs-lookup"><span data-stu-id="ebdd2-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="ebdd2-107">Grâce à Office 365, vous pouvez permettre aux utilisateurs d’installer Skype entreprise pour eux-mêmes à partir du portail Office 365.</span><span class="sxs-lookup"><span data-stu-id="ebdd2-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="ebdd2-108">Vous pouvez aussi déployer Skype entreprise pour vos utilisateurs en téléchargeant le logiciel sur votre réseau local, puis en utilisant vos outils de déploiement de logiciels existants, tels que Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="ebdd2-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="ebdd2-109">Pour plus d’informations sur l’installation de Skype entreprise qui est fourni avec Office 365, voir [déployer le client Skype entreprise dans office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="ebdd2-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="ebdd2-110">**Licence en volume** Si vous disposez d’une version sous licence en volume du client Skype entreprise 2015 ou 2016, la technologie d’installation qui est utilisée est le programme d’installation Windows (MSI).</span><span class="sxs-lookup"><span data-stu-id="ebdd2-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="ebdd2-111">Un package d’installation basé sur Windows Installer comporte plusieurs fichiers MSI.</span><span class="sxs-lookup"><span data-stu-id="ebdd2-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="ebdd2-112">Un package MSI de base indépendant de la langue est associé à un ou plusieurs packages spécifiques à la langue pour créer un produit complet.</span><span class="sxs-lookup"><span data-stu-id="ebdd2-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="ebdd2-113">La configuration assemble les packages individuels et effectue des tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ebdd2-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="ebdd2-114">Le client Skype entreprise 2019 utilise des programmes de installation «démarrer en un clic».</span><span class="sxs-lookup"><span data-stu-id="ebdd2-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="ebdd2-115">Les rubriques de cette section expliquent comment utiliser et personnaliser Windows Installer pour déployer le client Skype entreprise auprès de vos utilisateurs dans le cadre de vos procédures normales.</span><span class="sxs-lookup"><span data-stu-id="ebdd2-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ebdd2-116">Le complément réunion Skype pour Microsoft Office, qui prend en charge la gestion de la réunion à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec les clients Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="ebdd2-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ebdd2-117">Le programme d’installation d’Office 365 ne désinstalle pas les versions précédentes de Lync.</span><span class="sxs-lookup"><span data-stu-id="ebdd2-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="ebdd2-118">Le client Skype entreprise est installé côte à côte avec d’autres clients Lync.</span><span class="sxs-lookup"><span data-stu-id="ebdd2-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="ebdd2-119">Installation de clients Windows</span><span class="sxs-lookup"><span data-stu-id="ebdd2-119">Installing Windows clients</span></span>

- [<span data-ttu-id="ebdd2-120">Personnaliser l’installation du client Windows dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ebdd2-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="ebdd2-121">Configure the client experience with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ebdd2-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="ebdd2-122">Configuration de la liste de contacts dynamiques dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ebdd2-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="ebdd2-123">Installation de clients d’appareils</span><span class="sxs-lookup"><span data-stu-id="ebdd2-123">Installing device clients</span></span>

- [<span data-ttu-id="ebdd2-124">Skype Entreprise Server 2015 : installation et test de Skype Entreprise pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="ebdd2-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="ebdd2-125">Installation et test de Skype Entreprise pour iOS</span><span class="sxs-lookup"><span data-stu-id="ebdd2-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="ebdd2-126">Déploiement du plug-in Lync VDI avec Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ebdd2-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="ebdd2-127">Déploiement de clients Web à télécharger dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ebdd2-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="ebdd2-128">Personnaliser l'expérience de client Mac dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="ebdd2-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="ebdd2-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ebdd2-129">See also</span></span>

[<span data-ttu-id="ebdd2-130">Déploiement du client Skype entreprise dans Office 365</span><span class="sxs-lookup"><span data-stu-id="ebdd2-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
