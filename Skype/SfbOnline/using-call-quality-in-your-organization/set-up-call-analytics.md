---
title: Paramétrer Skype pour Analytique d’appeler commerciale
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
description: Configurer et utiliser des Analytique d’appel pour identifier et résoudre les problèmes de Skype pour les problèmes de qualité d’appel Business et Teams de Microsoft.
ms.openlocfilehash: 6e4566198e140c94da40f4db1a890eb4190d5da3
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="set-up-skype-for-business-call-analytics"></a>Paramétrer Skype pour Analytique d’appeler commerciale

Comme un Skype pour l’administration d’entreprise en ligne, vous pouvez utiliser Analytique d’appel pour résoudre les problèmes de Skype pour les entreprises, et Microsoft Teams appel à des problèmes de qualité et de la connexion. Vous pouvez trouver utile de configurer les fonctions suivantes dans Analytique d’appeler :
  
- Définir des autorisations qui vous permettent d’autres membres du personnel, tels que les agents du support technique, utilisez Analytique d’appel, mais les empêcher d’accéder à la suite de la Skype pour le centre d’administration de Business. 
    
- Ajouter des informations de locataire, du site et construction pour appeler l’Analytique en téléchargeant un fichier de données .tsv ou .csv.
    
> [!NOTE]
> Analytique de l’appel est en cours d’aperçu. Texte et images décrites ici peut ne pas correspondent de votre expérience. 
  
## <a name="set-call-analytics-permissions"></a>Définir les autorisations d’appeler l’Analytique
<a name="BKMK_SetCAPerms"></a>

En tant que l’administrateur, vous obtenez un accès complet à toutes les fonctionnalités d’appeler l’Analytique. En outre, vous pouvez utiliser un modèle de support technique dans appeler Analytique qui comprend les groupes d’autorisations du niveau 1 et niveau 2. Utilisateurs disposant des autorisations de niveau 1 peuvent accéder uniquement une vue limitée d’Analytique d’appeler. Utilisateurs disposant des autorisations de niveau 2 peuvent accéder à toutes les fonctionnalités d’appeler l’Analytique. Les deux niveaux d’autorisation empêche l’accès au reste de la Skype pour le centre d’administration commerciale. Vous pouvez accorder l’accès aux niveaux en ajoutant un groupe qui contient l’utilisateur pour le niveau 1 ou de la section de niveau 2 de la page autorisations. Pour plus d’informations, consultez [définition d’autorisations hiérarchisées Analytique d’appeler](set-up-call-analytics.md#BKMK_SetUpTier).
  
Agents de support technique de niveau 1 traite les problèmes de qualité de l’appel base. Les agents de niveau 1 n’étudier des problèmes avec des réunions ; Ils collectent des informations connexes et les transmettent à un agent de niveau 2. Agents de niveau 2 voir les journaux d’appel détaillés qui est masqué par les agents de niveau 1. Le tableau suivant donne une vue d’ensemble des informations disponibles pour les agents à l’aide d’appeler l’Analytique.


|**Activité**|**Informations d’appel Analytique**|**Ce que voit l’agent de niveau 1**|**Ce que voit l’agent de niveau 2**|
|:-----|:-----|:-----|:-----|
|**Appels** <br/> |Nom de l’appelant  <br/> |Seul le nom de l’utilisateur pour lequel l’agent de recherche.  <br/> |Nom d’utilisateur.  <br/> |
||Nom du destinataire  <br/> |Indique que l’utilisateur interne ou externe.  <br/> |Nom du destinataire.  <br/> |
||Numéro de téléphone de l’appelant  <br/> |Numéro entier, à l’exception des trois derniers chiffres sont obscurcis à l’aide des symboles d’astérisque. Par exemple, 15552823 ***.  <br/> |Numéro entier, à l’exception des trois derniers chiffres sont obscurcis à l’aide des symboles d’astérisque. Par exemple, 15552823 ***.  <br/> |
||Numéro de téléphone du destinataire  <br/> |Numéro entier, à l’exception des trois derniers chiffres sont obscurcis à l’aide des symboles d’astérisque. Par exemple, 15552823 ***.  <br/> |Numéro entier, à l’exception des trois derniers chiffres sont obscurcis à l’aide des symboles d’astérisque. Par exemple, 15552823 ***.  <br/> |
||**Détails de l’appel** > onglet**Avancé** <br/> |Informations non affichées.  <br/> |Tous les détails sont affichés, tels que les noms de périphériques, adresse IP, mappage de sous-réseau et bien plus encore.  <br/> |
||**Détails de l’appel** > **Avancé** > onglet**Déboguer** <br/> |Informations non affichées.  <br/> |Tous les détails sont affichés, tels que le suffixe DNS et le SSID.  <br/> |
|**Réunions** <br/> |Noms des participants  <br/> |Seul le nom de l’utilisateur pour lequel l’agent de recherche. Autres participants identifiés en tant qu’utilisateur interne ou externe.  <br/> |Tous les noms affichés.  <br/> |
||Nombre de participants  <br/> |Nombre de participants.  <br/> |Nombre de participants.  <br/> |
||Détails de la session  <br/> |Détails de la session avec exceptions. Uniquement le nom de l’utilisateur pour lequel l’agent de recherche s’affiche. Autres participants identifiés en tant qu’utilisateur interne ou externe. Dernière des trois chiffres du numéro de téléphone obscurcis à l’aide des symboles d’astérisque.  <br/> |Détails de session indiqués. Noms d’utilisateur et les détails de la session indiqués. Dernière des trois chiffres du numéro de téléphone obscurcis à l’aide des symboles d’astérisque.  <br/> |
   
 **Définition d’autorisations hiérarchisées Analytique d’appeler** 
 <a name="BKMK_SetUpTier"> </a>
  
1. Créer des groupes de sécurité d’Office 365 pour le niveau 1 et niveau 2, et ajoutez les personnes que vous souhaitez à chaque groupe. Vous pouvez également réutiliser des groupes de sécurité existants. Pour plus d’informations, voir [créer, modifier ou supprimer un groupe de sécurité dans le centre d’administration Office 365](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).
    
2. Dans le centre d’administration Office 365, accédez au **Centre d’administration** > **Skype pour les entreprises**.
    
    > [!NOTE]
    > Si vous placer dans l’ancien Skype pour le centre d’administration Business, atteindre la nouvelle version en cliquant sur **proviennent d’essayer notre nouveau centre d’administration**. 
  
3. Dans le nouveau Skype pour Business admin center, cliquez sur **autorisations**.
    
4. Ajoutez les groupes de sécurité d’Office 365 dans les zones de **niveau 1** et **niveau 2** . Vous pouvez ajouter plusieurs groupes pour chaque rôle.
    
     ![Capture d’écran montre les autorisations pour la page d’appeler l’Analytique avec les options pour les autorisations de niveau 1 et niveau 2.](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
 Les utilisateurs disposant d’un de ces niveaux d’autorisation accèdent à appeler l’Analytique via l’URL dédié *https://adminportal.services.skypeforbusiness.com*.
  
## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Télécharger un fichier .tsv ou .csv pour ajouter la création d’un site et le client les informations
<a name="BKMK_UploadFiles"> </a>

Vous pouvez ajouter de construction, du site et des informations de locataire pour appeler l’Analytique en téléchargeant un fichier .csv ou .tsv. Avec toutes ces informations, appelez l’Analytique peut mapper les adresses IP à des emplacements physiques. Vous, ou le support technique agents peuvent trouver ces informations utiles pour identifier les tendances des problèmes d’appel. Par exemple, pourquoi ressemblent beaucoup d’utilisateurs dans le même bâtiment ayant appeler des problèmes de qualité ? 
  
![Capture d’écran montre la page Sites, avec les valeurs de nombre de sites et le nombre de sous-réseaux et le bouton de sélection de fichier pour importer les données du site en téléchargeant un .tsv ou .csv.](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
Si vous êtes un Skype pour l’administration de l’entreprise, vous pouvez utiliser un fichier de données existant à partir de la Skype pour entreprise en ligne appeler tableau de bord qualité. Tout d’abord, vous téléchargez le fichier à partir du tableau de bord qualité appeler, et vous le téléchargez à appeler l’Analytique. Pour télécharger un fichier de données existant, accédez à la **Skype pour le centre d’administration de Business** > **Outils** > **Skype pour entreprise en ligne appeler tableau de bord qualité** > **Télécharger maintenant**. Dans la liste de **Mes téléchargements** , cliquez sur **Télécharger** en regard du fichier que vous souhaitez.
  
Si vous créez le fichier .tsv ou .csv à partir de zéro, voir le [format et la structure de fichier de données de création du fichier de données de clients](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Rubriques connexes
<a name="BKMK_UploadFiles"> </a>

[Utiliser l'analyse des appels pour résoudre les problèmes liés à la qualité médiocre des appels Skype Entreprise](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[En quoi l'analyse des appels et le tableau de bord de qualité des appels sont-ils différents ?](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 