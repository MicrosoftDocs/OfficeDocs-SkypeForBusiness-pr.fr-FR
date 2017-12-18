---
title: "Configurer Skype pour les entreprises appeler Analytique"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
description: "Set up and use Call Analytics to identify and troubleshoot Skype for Business and Microsoft Teams call quality problems."
---

# Configurer Skype pour les entreprises appeler Analytique

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
En tant qu'un administrateur Skype Entreprise Online, vous pouvez utiliser Analytique appeler pour résoudre les Skype Entreprise et Microsoft Teams problèmes de connexion et de la qualité de l'appel. Vous pouvez trouver utile de configurer les fonctionnalités suivantes dans appeler Analytique :
  
- Définir des autorisations qui vous permettent d'autres membres du personnel, tels que « agents » du support technique, utilisent appeler Analytique, mais les empêchent d'accéder au reste du centre d'administration Skype Entreprise.
    
- Ajoutez construction, du site et les informations de client pour appeler Analytique en téléchargeant un fichier de données .tsv ou .csv.
    
> [!NOTE]
> Appel Analytique est en cours d'aperçu. Texte et les images ci-dessus peut ne pas correspondent votre expérience. 
  
## Définir des autorisations d'appel Analytique
<a name="BKMK_SetCAPerms"> </a>

En tant qu'administrateur, vous obtenez un accès complet à toutes les fonctionnalités d'appel Analytique. En outre, vous pouvez utiliser un modèle de support technique dans Analytique appeler incluant des groupes d'autorisations du niveau 1 et niveau 2. Les utilisateurs disposant d'autorisations de niveau 1 peuvent accéder qu'une vue limitée d'Analytique appeler. Utilisateurs avec des autorisations de niveau 2 peuvent accéder à toutes les fonctionnalités d'appel Analytique. Les deux niveaux d'autorisation empêche l'accès au reste du centre d'administration Skype Entreprise. Vous pouvez accorder l'accès pour les couches en ajoutant un groupe qui contient l'utilisateur pour le niveau 1 ou de la section niveau 2 de la page des autorisations. Pour plus d'informations, voir [configurer les autorisations hiérarchisées dans Analytique appeler](fbf7247a-84ae-46cc-9204-2c45b1c734cd.md#BKMK_SetUpTier).
  
Agents de support technique de niveau 1 traiter les problèmes de qualité des appels de base. Agents de niveau 1 n'étudier des problèmes avec des réunions ; ils recueillir les informations connexes et remontez à un agent de niveau 2. Agents de niveau 2 affichent les informations dans les journaux d'appels détaillés qui ne sont pas agents de niveau 1. Le tableau suivant donne un aperçu des informations disponibles à agents à l'aide d'appeler Analytique.
  
|
|
|**Activité**|**Informations contenues dans appel Analytique**|**Ce que voit l'agent de niveau 1**|**Ce que voit l'agent de niveau 2**|
|:-----|:-----|:-----|:-----|
|**Appels** <br/> |Nom de l'appelant  <br/> |Uniquement le nom de l'utilisateur pour lequel l'agent de recherche.  <br/> |Nom d'utilisateur.  <br/> |
||Nom du destinataire  <br/> |Affiche les comme utilisateur interne ou externes.  <br/> |Nom du destinataire.  <br/> |
||Numéro de téléphone de l'appelant  <br/> |Numéro de téléphone entière à l'exception des trois derniers chiffres sont masquées par des symboles astérisque. Par exemple, 15552823 ***.  <br/> |Numéro de téléphone entière à l'exception des trois derniers chiffres sont masquées par des symboles astérisque. Par exemple, 15552823 ***.  <br/> |
||Numéro de téléphone du destinataire  <br/> |Numéro de téléphone entière à l'exception des trois derniers chiffres sont masquées par des symboles astérisque. Par exemple, 15552823 ***.  <br/> |Numéro de téléphone entière à l'exception des trois derniers chiffres sont masquées par des symboles astérisque. Par exemple, 15552823 ***.  <br/> |
||**Détails de l'appel** > onglet **Avancé** <br/> |Informations ne pas affichées.  <br/> |Toutes les informations affichées, tels que les noms d'appareil, adresse IP, mappage sous-réseau et plus.  <br/> |
||**Détails de l'appel** > **Avancé** > onglet **Déboguer** <br/> |Informations ne pas affichées.  <br/> |Toutes les informations affichées, par exemple SSID et suffixe DNS.  <br/> |
|**Réunions** <br/> |Noms des participants  <br/> |Uniquement le nom de l'utilisateur pour lequel l'agent de recherche. Autres participants identifiés comme utilisateur internes ou externes.  <br/> |Tous les noms affichés.  <br/> |
||Nombre de participants  <br/> |Nombre de participants.  <br/> |Nombre de participants.  <br/> |
||Détails de la session  <br/> |Détails de la session avec exceptions. Uniquement le nom de l'utilisateur pour lequel l'agent recherché s'affiche. Autres participants identifiés comme utilisateur internes ou externes. Derniers trois chiffres de numéro de téléphone brouillé par des symboles astérisque.  <br/> |Détails de la session indiqués. Noms d'utilisateur et les détails de la session indiqués. Derniers trois chiffres de numéro de téléphone brouillé par des symboles astérisque.  <br/> |
   
 **Définition d'autorisations hiérarchisées Analytique appeler**
  
1. Créer des groupes de sécurité Office 365 de niveau 1 et niveau 2, et ajoutez les personnes que vous souhaitez à chaque groupe. Vous pouvez également réutiliser les groupes de sécurité existants. Pour plus d'informations, voir [Créer, modifier ou supprimer un groupe de sécurité dans le centre d'administration Office 365](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).
    
2. Dans la Centre d'administration Office 365, accédez à **Centre d'administration** > **Skype entreprise**.
    
    > [!NOTE]
    > Si la page d'arrivée dans le centre d'administration Skype Entreprise ancien, accédez à la nouvelle version en cliquant sur **fournis Essayez notre nouveau centre d'administration**. 
  
3. Dans le centre d'administration Skype Entreprise nouveau, cliquez sur **autorisations**.
    
4. Ajoutez les groupes de sécurité Office 365 aux boîtes de **niveau 1** et **niveau 2**. Vous pouvez ajouter plusieurs groupes pour chaque rôle.
    
     ![Screenshot shows the Permissions for Call Analytics page with the options for Tier 1 and Tier 2 permissions.](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
Les utilisateurs avec une de ces niveaux d'autorisation atteindre Analytique appel via le https://adminportal.services.skypeforbusiness.com URL dédié.
  
## Télécharger un fichier .tsv ou .csv pour ajouter la création d'un site et des informations du client
<a name="BKMK_UploadFiles"> </a>

Vous pouvez ajouter construction, du site et les informations de client pour appeler Analytique en téléchargeant un fichier .csv ou .tsv. Avec toutes ces informations, appelez Analytique pouvez mapper des adresses IP à des emplacements physiques. Vous ou le support technique agents peuvent être utiles ces informations pour vous aider à identifier les tendances dans les problèmes d'appel. Par exemple, pourquoi d'utilisateurs dans le même bâtiment ayant sont similaires appeler les problèmes de qualité ?
  
![Screenshot shows the Sites page with values for Number of sites and Number of subnets, and the Select file button to import site data by uploading a .tsv or a .csv file.](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
Si vous êtes un administrateur Skype Entreprise, vous pouvez utiliser un fichier de données à partir de l'appel du tableau de bord qualité Skype Entreprise Online. Tout d'abord, vous téléchargez le fichier à partir de l'appel du tableau de bord qualité et puis vous téléchargez sur appeler Analytique. Pour télécharger un fichier de données existant, accédez à l' **Skype centre d'administration d'entreprise** > **Outils** > **Skype pour entreprise Online appeler la qualité du tableau de bord** > **Télécharger maintenant**. Dans la liste **Mes téléchargements**, cliquez sur **Télécharger** en regard du fichier souhaité.
  
Si vous créez le fichier .tsv ou .csv à partir de zéro, voir [Format du fichier de données client et structure du fichier de données du bâtiment](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md#BKMK_TenantDataFile).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  
## Voir aussi
<a name="MT_Footer"> </a>

#### 

[Qualité des appels utilisation appeler Analytique pour résoudre un problème Skype pour les entreprises](use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality.md)
  
[Quelle est la différence entre appeler Analytique et tableau de bord qualité d'appel ?](what-s-the-difference-between-call-analytics-and-call-quality-dashboard.md)

