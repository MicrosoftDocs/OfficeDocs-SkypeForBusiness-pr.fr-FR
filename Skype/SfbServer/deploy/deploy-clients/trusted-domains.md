---
title: Domaines approuvés de Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Consultez cette rubrique pour apprendre à configurer des domaines approuvés pour Skype Room System et Skype Entreprise.
ms.openlocfilehash: a63ecbfe9ed8e71656bd21988e297897b62e9cf3
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775239"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="152e8-103">Domaines approuvés de Skype Room System</span><span class="sxs-lookup"><span data-stu-id="152e8-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="152e8-104">Consultez cette rubrique pour apprendre à configurer des domaines approuvés pour Skype Room System et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="152e8-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="152e8-105">Domaines approuvés</span><span class="sxs-lookup"><span data-stu-id="152e8-105">Trusted domains</span></span>

<span data-ttu-id="152e8-106">Le client Skype entreprise affiche une boîte de dialogue permettant aux utilisateurs d’accepter le certificat du serveur Skype entreprise si le domaine SIP du compte d’utilisateur qui se connecte est différent du nom figurant dans le nom de l’objet ou de l’objet du certificat.</span><span class="sxs-lookup"><span data-stu-id="152e8-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="152e8-107">Si le certificat configuré pour Skype entreprise Server au sein de votre organisation n’a pas de nom de domaine SIP pour le compte système de salle Skype pour le nom de domaine de l’objet ou du sujet, vous devez configurer les domaines présentés sur le certificat sous domaines approuvés. clé de Registre sur la machine de la console du système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="152e8-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="152e8-108">Le Guide de l’administrateur système de salle Skype fourni par le fabricant vous explique comment et où ajouter des domaines approuvés dans le client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="152e8-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="152e8-109">Par exemple, supposons que les certificats configurés sur Skype entreprise Server possèdent le nom d’objet/de l’objet « CONTOSO ». LOCALE» et l’un des domaines SIP attribués à un utilisateur pour l’adresse de connexion de votre système de salle Skype est « confrm1@contoso.net ».</span><span class="sxs-lookup"><span data-stu-id="152e8-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="152e8-110">Dans la mesure où contoso.net ne figure pas dans le certificat, vous devez configurer « contoso. local » en tant que domaine approuvé dans le registre, comme indiqué dans le Guide de l’administrateur de votre système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="152e8-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

