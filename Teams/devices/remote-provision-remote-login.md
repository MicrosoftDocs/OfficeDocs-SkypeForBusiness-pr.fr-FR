---
title: Approvisionnement à distance et connexion pour les appareils Teams Android
author: dstrome
ms.author: dstrome
manager: serdars
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
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment approvisionner à distance et se connecter à des appareils Teams Android
ms.openlocfilehash: 5a746e3255ce8af9bcf59f8dfcae12854b222a1f
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761286"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Approvisionnement à distance et connexion pour les appareils Teams Android

Les administrateurs informatiques peuvent approvisionner et se connecter à distance à un appareil Teams Android. Pour approvisionner un appareil à distance, l’administrateur doit charger les ID MAC des appareils en cours d’approvisionnement et créer un code de vérification. L’ensemble du processus peut être effectué à distance à partir du centre d’administration Teams.

## <a name="review-the-supported-devices"></a>Passer en revue les appareils pris en charge

La liste suivante présente les exigences du microprogramme d’appareil Android.

|Catégorie d’appareil|Modèle d’appareil|Version du microprogramme|
|---|---|---|
|téléphones Teams|Yealink T55/T56/T58|58.15.0.124|
|téléphones Teams|Yealink VP59|91.15.0.58|
|téléphones Teams|Yealink CP960|73.15.0.117|
|téléphones Teams|Yealink MP56/MP54/MP58|122.15.0.36|
|téléphones Teams|Crestron UC-2|1.0.3.52|
|téléphones Teams|Poly Trio C60|7.0.2.1071|
|téléphones Teams|CCX400/CCX500/CCX600 |7.0.2.1072|
|téléphones Teams|Audio Codes C448HD/C450HD/C470HD|1.10.120|
|panneaux Teams|Crestron 770/1070|1.004.0115|
|salles Teams sur Android|Logitech Rally Bar Mini|1.2.982|
|salles Teams sur Android|Logitech Rally Bar|1.2.982|
|salles Teams sur Android|AudioCodes RXV80|1.13.361|
|salles Teams sur Android|EPOS EXPAND Vision 3T|1.2.2.21182.10|
|salles Teams sur Android|Yealink MeetingBar A30|133.15.0.60|
|salles Teams sur Android|Yealink MeetingBar A20|133.15.0.60|
|salles Teams sur Android|Console tactile Yealink CTP18|137.15.0.37|
|salles Teams sur Android|Poly Studio X30|3.5.0.344025|
|salles Teams sur Android|Poly Studio X50|3.5.0.344025|
|salles Teams sur Android|Console tactile Poly TC8 |3.5.0.210489|
|salles Teams sur Android|Yealink VC210|118.15.0.54|

## <a name="add-a-device-mac-address"></a>Ajouter une adresse MAC d’appareil

Effectuez les étapes suivantes pour approvisionner un nouvel appareil.

1. Se connecter au Centre d’administration de Microsoft Teams.
2. Développez **Teams appareils**.
3. Sélectionnez **Provisionner un nouvel appareil** dans l’onglet **Actions** .

Dans la fenêtre **Approvisionner de nouveaux appareils** , vous pouvez ajouter l’adresse MAC manuellement ou charger un fichier.

### <a name="manually-add-a-device-mac-address"></a>Ajouter manuellement une adresse MAC d’appareil

1. Sous l’onglet **En attente d’activation** , **sélectionnez Ajouter un ID MAC**.

   ![ajouter manuellement une adresse mac d’appareil.](../media/remote-provision-6-new.png)

1. Entrez l’ID MAC.
1. Entrez un emplacement, qui permet aux techniciens d’identifier où installer les appareils.
1. Sélectionnez **Appliquer** lorsque vous avez terminé.

### <a name="upload-a-file-to-add-a-device-mac-address"></a>Télécharger un fichier pour ajouter une adresse MAC d’appareil

1. Sous l’onglet **En attente d’activation**, sélectionnez **Télécharger ID MAC**.
2. Téléchargez le modèle de fichier.
3. Entrez l’ID MAC et l’emplacement, puis enregistrez le fichier.
4. **Sélectionnez fichier**, puis **sélectionnez Télécharger**.

## <a name="generate-a-verification-code"></a>Générer un code de vérification

Vous avez besoin d’un code de vérification pour les appareils. Le code de vérification est généré en bloc ou au niveau de l’appareil et est valide pendant 24 heures.

1. Sous l’onglet **En attente d’activation** , sélectionnez un ID MAC existant.
   Un mot de passe est créé pour l’adresse MAC et est affiché dans la colonne **Code de vérification** .

2. Fournissez la liste des ID MAC et des codes de vérification aux techniciens de terrain. Vous pouvez exporter les détails directement dans un fichier et partager le fichier avec le technicien qui effectue le travail d’installation réel.

## <a name="provision-the-device"></a>Provisionner l’appareil

Lorsque l’appareil est sous tension et connecté au réseau, le technicien provisionne l’appareil. Ces étapes sont effectuées sur l’appareil Teams.

1. Le technicien sélectionne **Provisionner l’appareil** dans le **Paramètres**.  

   ![Provisionnez une nouvelle option d’appareil à partir de l’onglet Actions.](../media/provision-device1.png)
  
2. Le technicien entre le code de vérification propre à l’appareil dans le champ d’entrée fourni.

   ![Provisionnez la vérification du nouvel appareil.](../media/provision-device-verification1.png)

   Une fois l’appareil correctement approvisionné, le nom du locataire apparaît sur la page de connexion.

   ![Nom du locataire dans la page de connexion.](../media/provision-code.png)

## <a name="first-time-remote-sign-in"></a>Première connexion à distance

L’appareil approvisionné s’affiche dans l’onglet **En attente de connexion** . Démarrez le processus de connexion à distance en sélectionnant l’appareil individuel.

1. Sélectionnez un appareil dans l’onglet **En attente de connexion** .

   ![Fenêtre avec une liste d’appareils prêts pour la connexion.](../media/remote-device1.png)

2. Suivez les instructions de connexion **d’un utilisateur**, puis sélectionnez **Fermer**.

   ![la fenêtre De connexion d’un utilisateur pour un appareil individuel.](../media/sign-in-user.png)

## <a name="related-articles"></a>Articles connexes

- [Gérer vos périphériques dans Teams](device-management.md)
- [Connexion à distance et déconnexion](remote-sign-in-and-sign-out.md)
- [Mettre à jour des appareils Teams à distance](remote-update.md)
