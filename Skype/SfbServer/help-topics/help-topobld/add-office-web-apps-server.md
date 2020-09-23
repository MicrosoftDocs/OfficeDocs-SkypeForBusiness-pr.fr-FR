---
title: Ajouter Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'L’Assistant définition d’un nouveau serveur Office Web Apps Server définit un nouveau serveur Office Web Apps Server dans votre déploiement. Vous devez fournir les informations suivantes :'
ms.openlocfilehash: 9e1726ea4b536e46fdbca5ec3eddce25358cbbbb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218725"
---
# <a name="add-office-web-apps-server"></a>Ajouter Office Web Apps Server

L’Assistant définition d’un **nouveau serveur Office Web Apps Server** définit un nouveau serveur Office Web Apps Server dans votre déploiement. Vous devez fournir les informations suivantes :

 Nom de domaine **complet (FQDN) d’Office Web Apps Server**: tapez le nom de domaine complet du serveur qui hébergera le serveur Office Web Apps Server.

 **URL de découverte d’Office Web Apps Server**: tapez l’URL (Uniform Resource Locator) complète du serveur Office Web Apps Server

> [!TIP]
> Le comportement par défaut de l' **URL de découverte d’Office Web Apps Server** consiste à créer l’URL basée sur le nom de domaine complet du serveur Office Web Apps Server au format suivant : `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Dans la plupart des cas, vous ne devrez pas modifier le format par défaut. Vous devrez peut-être modifier le format par défaut dans le cas où le serveur Office Web Apps Server et l’URL de découverte Office Web Apps Server doivent être différents. Par exemple, votre serveur Office Web Apps Server est placé dans le réseau de périmètre et aura une URL différente en fonction de l’emplacement.

 **Office Web Apps Server est déployé sur un réseau externe (périmètre/Internet)**: activez la case à cocher si votre serveur Office Web Apps Server est placé en dehors de votre pare-feu interne, tel que le réseau de périmètre, le réseau externe ou toute autre zone réseau différente de votre réseau interne.

## <a name="see-also"></a>Voir aussi

[Composants et topologies pour les conférences](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
