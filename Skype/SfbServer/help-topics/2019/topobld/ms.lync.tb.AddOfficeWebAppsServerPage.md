---
title: Ajouter Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'L’Assistant définir un nouveau serveur Office Web Apps définit un nouveau serveur Office Web Apps dans votre déploiement. Vous devez fournir les informations suivantes :'
ms.openlocfilehash: 9ca5be070d4a79a2cb011a1e91bd0613f21e8700
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798451"
---
# <a name="add-office-web-apps-server"></a>Ajouter Office Web Apps Server

L’Assistant **définir un nouveau serveur Office Web Apps** définit un nouveau serveur Office Web Apps dans votre déploiement. Vous devez fournir les informations suivantes :

 Nom de domaine **complet (FQDN) Office Web Apps Server**: tapez le nom de domaine complet du serveur qui héberge le serveur Office Web Apps.

 **URL de découverte d’Office Web Apps Server**: taper l’URL (Uniform Resource Locator) complète du serveur Office Web Apps

> [!TIP]
> Le comportement par défaut de l' **URL de découverte d’Office Web Apps Server** consiste à créer l’URL en fonction du nom de domaine complet (FQDN) du `https://<FQDN of the Office Web Apps Server/hosting/discovery` serveur Office Web Apps au format :. Dans la plupart des cas, vous ne devrez pas modifier le format par défaut. Il est possible que vous deviez modifier le format par défaut dans l’éventualité où Office Web Apps Server et l’URL de découverte du serveur Office Web Apps doivent être différents. Par exemple, votre serveur Office Web Apps est placé dans le réseau de périmètre et possède une autre URL en fonction de l’emplacement.

 **Office Web Apps Server est déployé sur un réseau externe (par exemple, périmètre/Internet)**: activez la case à cocher si votre serveur Office Web Apps est placé à l’extérieur de votre pare-feu interne, tel que le réseau de périmètre, le réseau externe ou une autre zone réseau qui n’est pas identique à votre réseau interne.

## <a name="see-also"></a>Voir aussi

[Components and Topologies for Conferencing](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
