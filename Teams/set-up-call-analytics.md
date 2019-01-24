---
title: Configurer Analytique d’appel
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Configurer et utiliser Analytique appeler pour identifier et résoudre les problèmes de Skype pour professionnels et Microsoft Teams problèmes de qualité d’appel.
ms.openlocfilehash: b2d6e6dc820e7cff7fa24858beb1de340704556e
ms.sourcegitcommit: 09fcd68e30e7f83110f98172382c74f970b339a7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/24/2019
ms.locfileid: "29442420"
---
# <a name="set-up-call-analytics"></a>Configurer Analytique d’appel

En une équipe ou Skype pour administrateur Business Online, vous pouvez utiliser Analytique appeler pour résoudre les problèmes de Skype pour les entreprises et des problèmes de connexion et de qualité des appels Microsoft Teams. Vous pouvez trouver utile de configurer les fonctionnalités suivantes dans l’appel d’Analytique :
  
- Définir des autorisations qui permettent d’autres membres du personnel, tels que les agents du support technique, utilisent Analytique appel, mais les empêchent d’accéder au reste de la & Microsoft Teams Skype entreprise centre d’administration. 
    
- Ajoutez génération, site et les informations de client pour appeler une Analytique en téléchargeant un fichier de données .tsv ou .csv.
    
**Appel Analytique est maintenant disponible dans le Microsoft Teams et Skype entreprise centre d’administration.** Pour afficher toutes les informations d’appel et les données d’un utilisateur, utilisez l’onglet **Historique des appels** . Pour cela, en effectuant une recherche sur la page de profil utilisateur en effectuant l’une des options suivantes :

- Recherche de l’utilisateur du tableau de bord.
  
   ![Capture d’écran de recherche d’un utilisateur sur le tableau de bord](media/set-up-call-analytics-image-1.png)

-  Sélectionnez **les utilisateurs** dans le volet de navigation gauche.

   ![Capture d’écran de navigation de gauche](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a>Définir des autorisations d’appel d’Analytique
<a name="BKMK_SetCAPerms"></a>

En tant que l’administrateur, vous obtenez un accès total à toutes les fonctionnalités d’appel d’Analytique. En outre, vous pouvez assigner des rôles d’Azure Active Directory au personnel de support. Attribuer le rôle de spécialiste de prise en charge de communications équipes aux utilisateurs qui doivent avoir une vue limitée d’Analytique d’appel. Attribuer le rôle de technicien de prise en charge de communications équipes aux utilisateurs qui ont besoin d’accéder à toutes les fonctionnalités d’appel d’Analytique. Les deux niveaux d’autorisation empêche l’accès au reste du & Microsoft Teams Skype entreprise centre d’administration.

> [!NOTE]
> Le rôle de spécialiste de prise en charge des communications est équivalent au support de niveau 1 et le rôle ingénieur de prise en charge des communications est équivalent au support de niveau 2.

Pour plus d’informations sur les rôles d’administration équipes, voir [utiliser les équipes Microsoft rôles d’administrateur pour gérer les équipes](using-admin-roles.md). 
  
Gérer les spécialistes du support de communications des problèmes fondamentaux de la qualité des appels. Ils n’examiner les problèmes liés à des réunions. Au lieu de cela, ils collecter des informations connexes et puis réaffecter à un ingénieur du support technique communications. Ingénieurs du support technique communications affichent les informations dans les journaux d’appels détaillées a masqué communications spécialistes du support. Le tableau suivant donne une vue d’ensemble des informations disponibles à communications prise en charge des spécialistes et communications ingénieurs lorsqu’ils utilisent Analytique d’appel.

|Activité|**Pour plus d’informations dans l’appel Analytique**|**Prendre en charge les communications spécialiste voit**|**Prendre en charge les communications ingénieur voit**|
|:-----|:-----|:-----|:-----|
|**Appels** <br/> |Nom de l’appelant  <br/> |Uniquement le nom de l’utilisateur pour lequel l’agent de recherche.  <br/> |Nom d'utilisateur  <br/> |
||Nom du destinataire  <br/> |Indique que l’utilisateur interne ou externe.  <br/> |Nom du destinataire.  <br/> |
||Numéro de téléphone de l’appelant  <br/> |Numéro de téléphone entier à l’exception des trois derniers chiffres sont obscurcis par des symboles astérisque. Par exemple, 15552823 ***.  <br/> |Numéro de téléphone entier à l’exception des trois derniers chiffres sont obscurcis par des symboles astérisque. Par exemple, 15552823 ***.  <br/> |
||Numéro de téléphone du destinataire  <br/> |Numéro de téléphone entier à l’exception des trois derniers chiffres sont obscurcis par des symboles astérisque. Par exemple, 15552823 ***.  <br/> |Numéro de téléphone entier à l’exception des trois derniers chiffres sont obscurcis par des symboles astérisque. Par exemple, 15552823 ***.  <br/> |
||**Détails de l’appel** > onglet**Avancé** <br/> |Informations non affichées.  <br/> |Tous les détails indiqués, tels que des noms de périphériques, adresse IP, mappage de sous-réseau et plus.  <br/> |
||**Détails de l’appel** > **Avancé** > onglet**Déboguer** <br/> |Informations non affichées.  <br/> |Tous les détails indiqués, tel que le suffixe DNS et SSID.  <br/> |
|Réunions <br/> |Noms des participants  <br/> |Uniquement le nom de l’utilisateur pour lequel l’agent de recherche. Autres participants identifiés comme utilisateur interne ou externe.  <br/> |Tous les noms indiqués.  <br/> |
||Nombre de participants  <br/> |Nombre de participants.  <br/> |Nombre de participants.  <br/> |
||Détails de la session  <br/> |Détails de la session avec les exceptions. Uniquement le nom de l’utilisateur pour lequel l’agent de recherche s’affiche. Autres participants identifiés comme utilisateur interne ou externe. Dernière trois chiffres du numéro de téléphone obscurcis par des symboles astérisque.  <br/> |Détails de la session indiqués. Noms d’utilisateur et les détails de la session indiqués. Dernière trois chiffres du numéro de téléphone obscurcis par des symboles astérisque.  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a>Définir des autorisations en attribuant des rôles d’administration
<a name="BKMK_SetUpTier"> </a>

Pour savoir comment attribuer des rôles administratifs dans Azure Active Directory, consultez la rubrique [Afficher et attribuer des rôles dans Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Télécharger un fichier .tsv ou .csv pour ajouter la création de sites et informations des clients
<a name="BKMK_UploadFiles"> </a>

Vous pouvez ajouter des informations client, du site et construction à Analytique appeler en téléchargeant un fichier .csv ou .tsv. Ces informations, Analytique appel peut mapper les adresses IP à des emplacements physiques. Vous ou du support technique agents pouvant être utiles ces informations aider à identifier les tendances des problèmes d’appel. Par exemple, pourquoi ressemblent nombre d’utilisateurs dans le même bâtiment ayant appeler des problèmes de qualité ? 

Si vous êtes un équipes et Skype pour l’administration de l’entreprise, vous pouvez utiliser un fichier de données existante à partir de la & équipes Skype pour Business appeler qualité de tableau de bord. Tout d’abord, vous téléchargez le fichier à partir du tableau de bord qualité des appels, puis vous le téléchargez dans Analytique d’appel. 

- Pour télécharger un fichier de données existant, accédez à **& équipes Microsoft Skype pour le centre d’administration Business** > **Appel du tableau de bord qualité** > **Télécharger maintenant**. Dans la liste **Mes téléchargements** , cliquez sur **Télécharger** en regard du fichier que vous souhaitez.

- Pour télécharger le nouveau fichier, accédez à **& équipes Microsoft Skype pour le centre d’administration Business** > **emplacements**et puis sélectionnez **télécharger les données d’emplacement** ou **Remplacer les données de localisation**.
  
Si vous créez le fichier .tsv ou .csv à partir de zéro, voir [format et la structure de fichier de données de création de fichiers de données client](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Rubriques connexes
<a name="BKMK_UploadFiles"> </a>

[Utiliser l'analyse des appels pour résoudre les problèmes liés à la qualité médiocre des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Appel Analytique et tableau de bord de qualité des appels](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
