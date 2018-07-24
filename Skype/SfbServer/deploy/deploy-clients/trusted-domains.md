---
title: Domaines approuvés de Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Consultez cette rubrique pour apprendre à configurer des domaines approuvés pour Skype Room System et Skype Entreprise.
ms.openlocfilehash: b55d1558bd45cc8f0726b054fed60b2a4c5e4794
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983762"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="306e7-103">Domaines approuvés de Skype Room System</span><span class="sxs-lookup"><span data-stu-id="306e7-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="306e7-104">Consultez cette rubrique pour apprendre à configurer des domaines approuvés pour Skype Room System et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="306e7-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="306e7-105">Domaines approuvés</span><span class="sxs-lookup"><span data-stu-id="306e7-105">Trusted domains</span></span>

<span data-ttu-id="306e7-106">Le Skype pour Business client affiche une boîte de dialogue qui permet aux utilisateurs d’accepter le certificat à partir de la Skype pour Business Server si le domaine SIP du compte d’utilisateur la signature est différent de celui présenté dans l’objet ou l’autre nom du sujet du certificat.</span><span class="sxs-lookup"><span data-stu-id="306e7-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="306e7-107">Si le certificat configuré pour Skype pour Business Server dans votre organisation ne dispose pas de nom de domaine SIP du compte de système de salle de Skype dans sujet ou autre nom du sujet, vous devez configurer ces domaines présentées dans le certificat sous les domaines approuvés clé de Registre sur l’ordinateur de la console Skype salle système.</span><span class="sxs-lookup"><span data-stu-id="306e7-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="306e7-108">Votre système de salle Skype fournie par le fabricant Skype salle Guide administrateur système explique comment et où pour ajouter des domaines approuvés dans le Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="306e7-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="306e7-109">Par exemple, supposons que les certificats configurés sur Skype pour Business Server dont le nom du sujet/objet Alt de « CONTOSO. « LOCALE » et un des domaines SIP attribuées à un utilisateur pour l’adresse de connexion Skype salle système est « confrm1@contoso.net ».</span><span class="sxs-lookup"><span data-stu-id="306e7-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="306e7-110">Car contoso.net n’est pas dans le certificat sur l’ordinateur du système de salle Skype, vous devez configurer « contoso.local » comme un domaine approuvé dans le Registre, comme expliqué dans votre système de salle Skype fournie par le fabricant Skype salle Guide administrateur système.</span><span class="sxs-lookup"><span data-stu-id="306e7-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

