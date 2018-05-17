---
title: Configurer Skype pour Business appeler Analytique
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Configurer et utiliser Analytique appeler pour identifier et résoudre les problèmes de Skype pour professionnels et Microsoft Teams problèmes de qualité d’appel.
ms.openlocfilehash: 0fea9e37933908ef64f1b2eb100f3851f84a6690
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2018
---
# <a name="set-up-skype-for-business-call-analytics"></a>Configurer Skype pour Business appeler Analytique

Comme un Skype pour administrateur Business Online, vous pouvez utiliser Analytique appeler pour résoudre les problèmes de Skype pour les entreprises et des problèmes de connexion et de qualité des appels Microsoft Teams. Vous pouvez trouver utile de configurer les fonctionnalités suivantes dans l’appel d’Analytique :
  
- Définir des autorisations qui vous permettent d’autres membres du personnel, tels que les agents de support technique, utilisez Analytique d’appel, mais les empêcher d’accéder au reste de la Skype entreprise centre d’administration. 
    
- Ajoutez génération, site et les informations de client pour appeler une Analytique en téléchargeant un fichier de données .tsv ou .csv.
    
> [!NOTE]
> Appel Analytique est actuellement en mode Aperçu. Texte et images décrites ici peut ne pas correspondent votre expérience. 
  
## <a name="set-call-analytics-permissions"></a>Définir des autorisations d’appel d’Analytique
<a name="BKMK_SetCAPerms"></a>

En tant que l’administrateur, vous obtenez un accès total à toutes les fonctionnalités d’appel d’Analytique. En outre, vous pouvez utiliser un modèle de support technique dans l’appel Analytique qui inclut les groupes d’autorisations de niveau 1 et niveau 2. Les utilisateurs disposant des autorisations de niveau 1 peuvent accéder uniquement une vue limitée d’Analytique d’appel. Les utilisateurs disposant des autorisations de niveau 2 peuvent accéder à toutes les fonctionnalités d’appel d’Analytique. Les deux niveaux d’autorisation empêche l’accès au reste du Skype entreprise centre d’administration. Vous pouvez accorder l’accès pour les niveaux en ajoutant un groupe qui contient l’utilisateur pour le niveau 1 ou de la section de niveau 2 de la page autorisations. Pour plus d’informations, voir [définir des autorisations à plusieurs niveaux dans Analytique d’appel](set-up-call-analytics.md#BKMK_SetUpTier).
  
Gérer les agents de support technique de niveau 1 des problèmes fondamentaux de la qualité des appels. Les agents de niveau 1 n’étudier des problèmes avec les réunions ; ils collecter des informations connexes et remontez à un agent de niveau 2. Agents de niveau 2 affichent les informations dans les journaux d’appels détaillées agents de niveau 1 sont masquées. Le tableau suivant donne une vue d’ensemble des informations disponibles à agents à l’aide d’Analytique d’appel.


|**Activité**|**Pour plus d’informations dans l’appel Analytique**|**Ce que voit l’agent de niveau 1**|**Ce que voit l’agent de niveau 2**|
|:-----|:-----|:-----|:-----|
|**Appels** <br/> |Nom de l’appelant  <br/> |Uniquement le nom de l’utilisateur pour lequel l’agent de recherche.  <br/> |Nom d’utilisateur.  <br/> |
||Nom du destinataire  <br/> |Indique que l’utilisateur interne ou externe.  <br/> |Nom du destinataire.  <br/> |
||Numéro de téléphone de l’appelant  <br/> |Numéro de téléphone entier à l’exception des trois derniers chiffres sont obscurcis par des symboles astérisque. Par exemple, 15552823 ***.  <br/> |Numéro de téléphone entier à l’exception des trois derniers chiffres sont obscurcis par des symboles astérisque. Par exemple, 15552823 ***.  <br/> |
||Numéro de téléphone du destinataire  <br/> |Numéro de téléphone entier à l’exception des trois derniers chiffres sont obscurcis par des symboles astérisque. Par exemple, 15552823 ***.  <br/> |Numéro de téléphone entier à l’exception des trois derniers chiffres sont obscurcis par des symboles astérisque. Par exemple, 15552823 ***.  <br/> |
||**Détails de l’appel** > onglet**Avancé** <br/> |Informations non affichées.  <br/> |Tous les détails indiqués, tels que des noms de périphériques, adresse IP, mappage de sous-réseau et plus.  <br/> |
||**Détails de l’appel** > **Avancé** > onglet**Déboguer** <br/> |Informations non affichées.  <br/> |Tous les détails indiqués, tel que le suffixe DNS et SSID.  <br/> |
|**Réunions** <br/> |Noms des participants  <br/> |Uniquement le nom de l’utilisateur pour lequel l’agent de recherche. Autres participants identifiés comme utilisateur interne ou externe.  <br/> |Tous les noms indiqués.  <br/> |
||Nombre de participants  <br/> |Nombre de participants.  <br/> |Nombre de participants.  <br/> |
||Détails de la session  <br/> |Détails de la session avec les exceptions. Uniquement le nom de l’utilisateur pour lequel l’agent de recherche s’affiche. Autres participants identifiés comme utilisateur interne ou externe. Dernière trois chiffres du numéro de téléphone obscurcis par des symboles astérisque.  <br/> |Détails de la session indiqués. Noms d’utilisateur et les détails de la session indiqués. Dernière trois chiffres du numéro de téléphone obscurcis par des symboles astérisque.  <br/> |
   
 **Définir des autorisations à plusieurs niveaux dans Analytique appeler** 
 <a name="BKMK_SetUpTier"> </a>
  
1. Créer des groupes de sécurité d’Office 365 niveau 1 et niveau 2, et ajoutez les personnes à inviter à chaque groupe. Vous pouvez également réutiliser les groupes de sécurité existants. Pour plus d’informations, voir [créer, modifier ou supprimer un groupe de sécurité dans le centre d’administration d’Office 365](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).
    
2. Dans le centre d’administration Office 365, accédez au **Centre d’administration** > **Skype pour les entreprises**.
    
    > [!NOTE]
    > Si vous atteindre dans l’ancienne Skype entreprise centre d’administration, accédez à la nouvelle version en cliquant sur **proviennent essayer notre nouveau centre d’administration**. 
  
3. Dans la nouvelle Skype entreprise centre d’administration, cliquez sur **autorisations**.
    
4. Ajoutez les groupes de sécurité Office 365 pour les zones de **niveau 1** et **niveau 2** . Vous pouvez ajouter plusieurs groupes à chaque rôle.
    
     ![Capture d’écran montre la page autorisations pour appeler les Analytique avec les options pour les autorisations de niveau 1 et niveau 2.](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
 Les utilisateurs avec une de ces niveaux d’autorisation accéder à appeler l’Analytique via l’URL dédié *https://adminportal.services.skypeforbusiness.com*.
  
## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Télécharger un fichier .tsv ou .csv pour ajouter la création de sites et informations des clients
<a name="BKMK_UploadFiles"> </a>

Vous pouvez ajouter des informations client, du site et construction à Analytique appeler en téléchargeant un fichier .csv ou .tsv. Ces informations, Analytique appel peut mapper les adresses IP à des emplacements physiques. Vous ou du support technique agents pouvant être utiles ces informations aider à identifier les tendances des problèmes d’appel. Par exemple, pourquoi ressemblent nombre d’utilisateurs dans le même bâtiment ayant appeler des problèmes de qualité ? 
  
![Capture d’écran montre la page Sites avec des valeurs pour le nombre de sites et le nombre de sous-réseaux et le bouton Sélectionner le fichier à importer des données de site en téléchargeant un .tsv ou dans un fichier .csv.](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
Si vous êtes un Skype pour administrateur d’entreprise, vous pouvez utiliser un fichier de données existante à partir de la Skype pour Business Online appeler qualité du tableau de bord. Tout d’abord, vous téléchargez le fichier à partir du tableau de bord qualité des appels, puis vous le téléchargez dans Analytique d’appel. Pour télécharger un fichier de données existant, accédez à la **Skype pour le centre d’administration Business** > **Outils** > **Skype pour Business Online appeler tableau de bord qualité** > **Télécharger maintenant**. Dans la liste **Mes téléchargements** , cliquez sur **Télécharger** en regard du fichier que vous souhaitez.
  
Si vous créez le fichier .tsv ou .csv à partir de zéro, voir [format et la structure de fichier de données de création de fichiers de données client](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Rubriques connexes
<a name="BKMK_UploadFiles"> </a>

[Utiliser l'analyse des appels pour résoudre les problèmes liés à la qualité médiocre des appels Skype Entreprise](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Appel Analytique et tableau de bord de qualité des appels](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 