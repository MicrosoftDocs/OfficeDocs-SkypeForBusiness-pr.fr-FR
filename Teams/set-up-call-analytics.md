---
title: Configurer l’analyse des appels
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configurez et utilisez l’analyse des appels pour identifier et résoudre les problèmes de qualité d’appel dans Skype entreprise et Microsoft Teams.
ms.openlocfilehash: fe46ee580554969d26395b26117649ab8ada2ea0
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838054"
---
# <a name="set-up-call-analytics"></a>Configurer l’analyse des appels

En tant qu’administrateur Skype entreprise Online, vous pouvez utiliser les services d’analyse des appels pour résoudre les problèmes de qualité d’appel et de connexion de Skype entreprise et Microsoft Teams. Il est possible que vous ayez besoin de configurer les fonctionnalités suivantes dans analyse d’appel :
  
- Définissez des autorisations qui permettent à d’autres utilisateurs, tels que les agents de support technique, d’utiliser l’analyse des appels, mais empêchez-les d’accéder au reste du centre d’administration Microsoft Teams. 
    
- Ajoutez des informations de bâtiment, de site et de client pour appeler des analyses en chargeant un fichier de données. TSV ou. csv.
    
**L’analyse des appels est désormais disponible dans le centre d’administration Microsoft teams**. Pour afficher toutes les informations d’appel et les données d’un utilisateur, utilisez l’onglet **historique des appels** . Pour cela, vous pouvez consulter la page de profil de l’utilisateur en effectuant l’une des opérations suivantes :

- Recherchez l’utilisateur dans le tableau de bord.
  
   ![Capture d’écran de la recherche de l’utilisateur dans le tableau de bord](media/set-up-call-analytics-image-1.png)

-  Dans le volet de navigation gauche, sélectionnez **utilisateurs** .

   ![Capture d’écran du volet de navigation gauche](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a>Définir des autorisations d’analyse d’appel
<a name="BKMK_SetCAPerms"></a>

En tant qu’administrateur, vous disposez d’un accès complet à toutes les fonctionnalités d’analyse des appels. De plus, vous pouvez attribuer des rôles Azure Active Directory à l’équipe de support technique. Affectez au rôle de spécialiste de la prise en charge des communications équipe aux utilisateurs qui doivent disposer d’un affichage limité de l’analyse des appels. Affectez au rôle de technicien de support communications de l’équipe aux utilisateurs qui ont besoin d’accéder à l’ensemble des fonctionnalités d’analyse des appels. Les deux niveaux d’autorisation empêchent l’accès au reste du centre d’administration Microsoft Teams.

> [!NOTE]
> Le rôle de spécialiste du support des communications est équivalent au support de niveau 1 et le rôle d’ingénieur de support des communications équivaut à la prise en charge de niveau 2.

Pour plus d’informations sur les rôles d’administrateur d’équipe, voir [utiliser les rôles d’administrateur Microsoft teams pour gérer teams](using-admin-roles.md). 
  
Les spécialistes de la prise en charge des communications traitent des problèmes de qualité d’appel. Ils ne recherchent pas les problèmes liés aux réunions. En revanche, il recueille des informations connexes, puis le transmet à un ingénieur du support des communications. Les ingénieurs de support des communications voient les informations contenues dans les journaux d’appels détaillés des spécialistes du support des communications. Le tableau suivant fournit une vue d’ensemble des informations accessibles aux spécialistes de la prise en charge des communications et aux ingénieurs du support des communications lorsqu’ils utilisent la technique d’analyse des appels.

|**Interactive**|**Informations dans analyse des appels**|**Ce que voit le spécialiste du support des communications**|**Ce que le technicien du support technique peut voir**|
|:-----|:-----|:-----|:-----|
|**Appels** <br/> |Nom de l’appelant  <br/> |Uniquement le nom de l’utilisateur pour lequel l’agent a effectué la recherche.  <br/> |Nom d’utilisateur.  <br/> |
||Nom du destinataire  <br/> |Affiche en tant qu’utilisateur interne ou utilisateur externe.  <br/> |Nom du destinataire.  <br/> |
||Numéro de téléphone de l’appelant  <br/> |Le numéro de téléphone complet sauf les trois derniers Par exemple, 15552823 * * *.  <br/> |Le numéro de téléphone complet sauf les trois derniers Par exemple, 15552823 * * *.  <br/> |
||Numéro de téléphone du destinataire  <br/> |Le numéro de téléphone complet sauf les trois derniers Par exemple, 15552823 * * *.  <br/> |Le numéro de téléphone complet sauf les trois derniers Par exemple, 15552823 * * *.  <br/> |
||**** > Onglet**avancé** des détails des appels <br/> |Informations non affichées.  <br/> |Tous les détails indiqués, tels que les noms des appareils, l’adresse IP, le mappage de sous-réseau, etc.  <br/> |
||**** > Onglet**débogage** **avancé** > détails des appels <br/> |Informations non affichées.  <br/> |Tous les détails indiqués, tels que les suffixes DNS et SSID.  <br/> |
|**Meetings** <br/> |Noms des participants  <br/> |Uniquement le nom de l’utilisateur pour lequel l’agent a effectué la recherche. Autres participants identifiés comme utilisateurs internes ou utilisateurs externes.  <br/> |Tous les noms affichés.  <br/> |
||Nombre de participants  <br/> |Nombre de participants.  <br/> |Nombre de participants.  <br/> |
||Détails de la session  <br/> |Détails de la session accompagnés d’exceptions. Uniquement le nom de l’utilisateur pour lequel la recherche de l’agent est affichée. Autres participants identifiés comme utilisateurs internes ou utilisateurs externes. Les trois derniers chiffres du numéro de téléphone brouillés par des symboles d’astérisque.  <br/> |Détails de la session affichés. Les noms d’utilisateur et les détails de la session apparaissent. Les trois derniers chiffres du numéro de téléphone brouillés par des symboles d’astérisque.  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a>Définir des autorisations en attribuant des rôles d’administrateur
<a name="BKMK_SetUpTier"> </a>

Pour plus d’informations sur l’attribution de rôles d’administrateur dans Azure Active Directory, voir [afficher et affecter des rôles dans Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Télécharger un fichier. TSV ou. csv pour ajouter des informations de bâtiment, de site et de client
<a name="BKMK_UploadFiles"> </a>

Vous pouvez ajouter des informations de bâtiment, de site et de client pour appeler des analyses en chargeant un fichier. csv ou. TSV. À l’aide de ces informations, l’analyse des appels permet de mapper les adresses IP aux emplacements physiques. Les agents de support technique ou vous-même trouverez ces informations utiles pour détecter les tendances en matière de problèmes d’appel. Par exemple, pourquoi de nombreux utilisateurs d’un même immeuble présentent-ils des problèmes de qualité d’appel similaires ? 

Si vous êtes un administrateur de équipes et Skype entreprise, vous pouvez utiliser un fichier de données existant à partir de l’équipe & tableau de bord de qualité des appels Skype entreprise. Tout d’abord, vous devez télécharger le fichier à partir du tableau de bord de qualité des appels, puis le charger pour appeler Analytics. 

- Pour**Télécharger un**fichier de données existant, accédez au centre > d' **administration Microsoft teams**de**qualité** > des appels. Dans la liste **Mes téléchargements** , cliquez sur **Télécharger** en regard du fichier souhaité.

- Pour télécharger le nouveau fichier, accédez à > **emplacements**du **Centre d’administration de Microsoft teams**, puis sélectionnez **charger les données d’emplacement** ou remplacer les données d' **emplacement**.
  
Si vous créez le fichier. TSV ou. csv à partir de zéro, voir [format de fichier de données client et structure du fichier de données](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Rubriques connexes
<a name="BKMK_UploadFiles"> </a>

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Tableau de bord Analyse des appels et Qualité des appels](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
