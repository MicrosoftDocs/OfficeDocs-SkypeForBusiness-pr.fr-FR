---
title: Mise en service à distance et se connectez pour les appareils Android Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser la mise en service à distance et la connectez-vous pour les appareils Android Teams
ms.openlocfilehash: 43a025c0cc68fb7f10015d69298f8dd75f9003e8
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410336"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Mise en service à distance et se connectez pour les appareils Android Teams

Les administrateurs informatiques peuvent mettre en service et se connectent à distance sur un appareil Teams Android. Pour mettre en service un appareil à distance, l’administrateur doit télécharger les ID MAC des appareils en cours de mise en service et créer un code de vérification. L’ensemble du processus peut être accompli à distance à partir du Centre d’administration Teams.

## <a name="review-the-supported-devices"></a>Passer en revue les appareils pris en charge

La liste suivante présente les conditions requises pour le microprogramme de l’appareil Android.

|Catégorie d’appareil|Modèle d’appareil|Version du microprogramme|
|-|-|-|
|Téléphones Teams|Yealink T55/T56/T58|58.15.0.124|
|Téléphones Teams|Yealink VP59|91.15.0.58|
|Téléphones Teams|Yealink CP960|73.15.0.117|
|Téléphones Teams|Yealink MP56/MP54/MP58|122.15.0.36|
|Téléphones Teams|Crestron UC-2|1.0.3.52|

## <a name="add-a-device-mac-address"></a>Ajouter une adresse MAC d’appareil

Pour mettre en service un nouvel appareil, vous suivrez les étapes suivantes.

1. Se connecter au Centre d’administration de Microsoft Teams.
2. Développez **Périphériques.**
3. Sélectionnez **Provision new device from** the **Actions** tab.

Dans la **fenêtre Provision de nouveaux appareils,** vous pouvez ajouter l’adresse mac manuellement ou charger un fichier.

### <a name="manually-add-a-device-mac-address"></a>Ajouter manuellement une adresse MAC de périphérique

1. Dans **l’onglet Activation en** attente, **sélectionnez Ajouter un ID MAC.**

   ![ajouter manuellement une adresse Mac de périphérique](../media/remote-provision-6.png)

1. Entrez l’ID MAC.
1. Entrez un emplacement pour aider les techniciens à identifier l’emplacement d’installation des appareils.
1. Sélectionnez **Appliquer** lorsque vous avez terminé.

### <a name="upload-a-file-to-add-a-device-mac-address"></a>Télécharger un fichier pour ajouter une adresse MAC d’appareil

1. Dans **l’onglet Activation en** attente, **sélectionnez Télécharger les ID MAC.**
2. Téléchargez le modèle de fichier.
3. Entrez l’ID MAC et l’emplacement, puis enregistrez le fichier.
4. **Sélectionnez le** fichier, puis **Charger.**

## <a name="generate-a-verification-code"></a>Générer un code de vérification

Vous avez besoin d’un code de vérification pour les appareils. Le code de vérification est généré en bloc ou au niveau de l’appareil et est valable pendant 24 heures.

1. Dans **l’onglet Activation** en attente, sélectionnez un ID MAC existant.
   Un mot de passe est créé pour l’adresse MAC et s’affiche dans la colonne **Code de** vérification.

2. Fournissez la liste des ID MAC et des codes de vérification aux techniciens de champ. Vous pouvez exporter les détails directement dans un fichier et le partager avec le technicien qui travaille sur l’installation réelle.

## <a name="provision-the-device"></a>Approvisionnement de l’appareil

Lorsque l’appareil est sous tension et connecté au réseau, le technicien le connecte. Ces étapes sont effectuées sur l’appareil Teams.

1. Le technicien sélectionne Périphérique **d’approvisionnement** dans **les paramètres.**  

   ![Option Nouvel appareil disponible à partir de l’onglet Actions](../media/provision-device1.png)
  
2. Le technicien entre le code de vérification spécifique de l’appareil dans le champ de saisie fourni.

   ![Vérification de l’approvisionnement d’un nouvel appareil](../media/provision-device-verification1.png)

   Une fois l’appareil correctement mis en service, le nom du client s’affiche sur la page de inscription.

   ![Nom du client sur la page de inscription](../media/provision-code.png)

## <a name="sign-in-remotely"></a>Se connectez à distance

Le périphérique en attente apparaît dans **l’onglet De confirmation de** la mise en service. Démarrez le processus de inscription à distance en sélectionnant le périphérique individuel.

1. Sélectionnez un appareil dans **l’onglet Se connectez en** attente.

   ![Fenêtre avec une liste d’appareils prêts à être connectés.](../media/remote-device1.png)

2. Suivez les instructions dans **Se connectez à un utilisateur,** puis sélectionnez **Fermer.**

   ![Fenêtre Se connectez à un utilisateur pour un appareil individuel](../media/sign-in-user.png)

## <a name="related-article"></a>Article connexe

- [Gérer vos périphériques dans Teams](device-management.md)
- [Mettre à jour les appareils Teams à distance](remote-update.md)
