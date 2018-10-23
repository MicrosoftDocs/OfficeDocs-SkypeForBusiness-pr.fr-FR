---
title: Domaines approuvés de Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Consultez cette rubrique pour apprendre à configurer des domaines approuvés pour Skype Room System et Skype Entreprise.
ms.openlocfilehash: bc025849f56a7257ac3684b9783e551959bd0228
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699685"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="9bf04-103">Domaines approuvés de Skype Room System</span><span class="sxs-lookup"><span data-stu-id="9bf04-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="9bf04-104">Consultez cette rubrique pour apprendre à configurer des domaines approuvés pour Skype Room System et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="9bf04-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="9bf04-105">Domaines approuvés</span><span class="sxs-lookup"><span data-stu-id="9bf04-105">Trusted domains</span></span>

<span data-ttu-id="9bf04-106">Le Skype pour Business client affiche une boîte de dialogue qui permet aux utilisateurs d’accepter le certificat à partir de la Skype pour Business Server si le domaine SIP du compte d’utilisateur la signature est différent de celui présenté dans l’objet ou l’autre nom du sujet du certificat.</span><span class="sxs-lookup"><span data-stu-id="9bf04-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="9bf04-107">Si le certificat configuré pour Skype pour Business Server dans votre organisation ne dispose pas de nom de domaine SIP du compte de système de salle de Skype dans sujet ou autre nom du sujet, vous devez configurer ces domaines présentées dans le certificat sous les domaines approuvés clé de Registre sur l’ordinateur de la console Skype salle système.</span><span class="sxs-lookup"><span data-stu-id="9bf04-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="9bf04-108">Votre système de salle Skype fournie par le fabricant Skype salle Guide administrateur système explique comment et où pour ajouter des domaines approuvés dans le Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="9bf04-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="9bf04-109">Par exemple, supposons que les certificats configurés sur Skype pour Business Server dont le nom du sujet/objet Alt de « CONTOSO. « LOCALE » et un des domaines SIP attribuées à un utilisateur pour l’adresse de connexion Skype salle système est « confrm1@contoso.net ».</span><span class="sxs-lookup"><span data-stu-id="9bf04-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="9bf04-110">Car contoso.net n’est pas dans le certificat sur l’ordinateur du système de salle Skype, vous devez configurer « contoso.local » comme un domaine approuvé dans le Registre, comme expliqué dans votre système de salle Skype fournie par le fabricant Skype salle Guide administrateur système.</span><span class="sxs-lookup"><span data-stu-id="9bf04-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

