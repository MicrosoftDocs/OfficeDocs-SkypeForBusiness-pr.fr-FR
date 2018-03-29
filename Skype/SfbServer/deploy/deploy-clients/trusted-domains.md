---
title: Domaines approuvés de Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Consultez cette rubrique pour apprendre à configurer des domaines approuvés pour Skype Room System et Skype Entreprise.
ms.openlocfilehash: 83d6e313f8643f593e1e25488e403da448649bd6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="9691e-103">Domaines approuvés de Skype Room System</span><span class="sxs-lookup"><span data-stu-id="9691e-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="9691e-104">Consultez cette rubrique pour apprendre à configurer des domaines approuvés pour Skype Room System et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="9691e-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="9691e-105">Domaines approuvés</span><span class="sxs-lookup"><span data-stu-id="9691e-105">Trusted domains</span></span>

<span data-ttu-id="9691e-106">Le Skype pour client d’entreprise affiche une boîte de dialogue qui permet aux utilisateurs d’accepter le certificat de la Skype pour Business Server si le domaine SIP de l’ouverture de session du compte d’utilisateur est différent de celui présenté dans l’objet ou le nom du sujet Alt sur le certificat.</span><span class="sxs-lookup"><span data-stu-id="9691e-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="9691e-107">Si le certificat configuré pour Skype pour Business Server dans votre organisation n’a pas de nom de domaine SIP du compte système local de Skype dans l’objet ou le nom de l’objet Alt, vous devez configurer ces domaines présentés sur le certificat dans les domaines approuvés clé de Registre sur l’ordinateur de la console système de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="9691e-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="9691e-108">Système de chambre de Skype fournie par le fabricant Skype espace système Guide de l’administrateur explique comment et où pour ajouter des domaines approuvés dans le Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="9691e-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="9691e-109">Par exemple, supposons que les certificats configurés sur Skype pour Business Server ont un nom objet/objet Alt « CONTOSO. « LOCAL » et l’un des domaines SIP affectés à un utilisateur pour l’adresse de connexion Skype espace système est « confrm1@contoso.net ».</span><span class="sxs-lookup"><span data-stu-id="9691e-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="9691e-110">Car contoso.net n’est pas dans le certificat sur l’ordinateur du système de salle de Skype, vous devez configurer des « contoso.local » sous la forme d’un domaine approuvé dans le Registre, comme expliqué dans Skype espace système fournie par le fabricant Skype espace système Guide de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="9691e-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

