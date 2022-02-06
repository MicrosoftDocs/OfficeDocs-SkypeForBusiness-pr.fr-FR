---
title: Ajouter Office Web Apps Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: "L’Assistant Définir Office Web Apps Server définit une nouvelle Office Web Apps Server dans votre déploiement. Vous devez fournir les informations suivantes\_:"
---

# <a name="add-office-web-apps-server"></a>Ajouter Office Web Apps Server

**L’Assistant Définir Office Web Apps Server** définit une nouvelle Office Web Apps Server dans votre déploiement. Vous devez fournir les informations suivantes :

 **Office de domaine complet du serveur Web Apps Server** : tapez le nom de domaine complet du serveur qui hébergera le serveur Office Web Apps Server

 **Office’URL** de découverte du serveur Web Apps Server : tapez l’URL (uniform resource locator) complète du serveur web Office Web Apps Server

> [!TIP]
> Le comportement par défaut de l’URL de découverte **Office Web Apps Server** consiste à créer l’URL en fonction du nom de domaine Office Web Apps Server au format `https://<FQDN of the Office Web Apps Server/hosting/discovery` : Dans la plupart des cas, vous ne devrez pas modifier le format par défaut. Vous devrez peut-être modifier le format par défaut si le serveur Office Web Apps Server et l’URL de découverte Office Web Apps Server doivent être différents. Par exemple, votre Office Web Apps Server est placé dans le réseau de périmètre et aura une URL différente en fonction de l’emplacement.

 **Office Web Apps Server** est déployé dans un réseau externe (périmètre/Internet) : cochez la case si votre serveur Office Web Apps Server est placé en dehors de votre pare-feu interne, tel que le réseau de périmètre, le réseau externe ou toute autre zone réseau qui n’est pas la même que votre réseau interne.

## <a name="see-also"></a>Voir aussi

[Composants et topologies pour les conférences](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)