---
title: Vérifier la topologie dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Résumé : Découvrez comment vérifier la Skype pour la topologie du serveur d’entreprise et serveurs Active Directory fonctionnent comme prévu. Téléchargez une version d’évaluation gratuite de Skype pour Business Server depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 03dfb45c03aa104cc5a9b265a37c347380590877
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32210794"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Vérifier la topologie dans Skype pour Business Server
 
**Résumé :** Découvrez comment vérifier la Skype pour la topologie du serveur d’entreprise et serveurs Active Directory fonctionnent comme prévu. Téléchargez une version d’évaluation gratuite de Skype pour Business Server à partir du [Centre d’évaluation de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Une fois que la topologie publiée et la Skype pour les composants du système Business Server installé sur chacun des serveurs dans la topologie, vous êtes prêt à vérifier que la topologie fonctionne comme prévu. Cela inclut de vérifier que la configuration est propagée à tous les serveurs Active Directory pour que la totalité du domaine sache que Skype pour les entreprises est disponible dans le domaine. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Cependant, vous devez réaliser les étapes 6, 7 et 8 dans l’ordre stipulé, après les étapes 1 à 5, comme indiqué dans le diagramme. La vérification de la topologie est la 8e des 8 étapes.
  
![Schéma de vue d’ensemble.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Test du déploiement de pool frontal

L’étape finale consiste à tester le pool frontal et confirmez que Skype pour les clients d’entreprise peut communiquer entre eux. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Ajout d’utilisateur et vérification de la connectivité entre les clients

1. Utilisez les utilisateurs et ordinateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle d’administrateur pour le Skype pour le déploiement de serveur d’entreprise (sur lequel est installé Skype pour le panneau de configuration serveur Business) au groupe **CSAdministrator** .
    
    > [!IMPORTANT]
    > Si vous n’ajoutez pas les utilisateurs et groupes appropriés au groupe CsAdministors, vous recevrez une erreur lorsque vous ouvrez Skype pour Business Server Control Panel qui lit, « non autorisé : accès refusé en raison d’un échec de l’autorisation d’accès basé sur un rôle RBAC (contrôle) ." 
  
2. Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.
    
    > [!NOTE]
    > Le compte d’utilisateur ne peut pas être administrateur local de n’importe quel serveur exécutant Skype pour Business Server. 
  
3. Utilisez le compte administratif pour ouvrir une session sur l’ordinateur où est installé Skype pour le panneau de configuration serveur Business.
    
4. Démarrez Skype pour Business Server le panneau de configuration, puis fournissez les informations d’identification, si vous y êtes invité. Skype pour Business Server Control Panel affiche les informations de déploiement.
    
5. Dans la barre de navigation de gauche, cliquez sur **la topologie**, puis vérifiez que l’état du service affiche un ordinateur avec une flèche verte et qu’une coche verte pour l’état de la réplication est en regard de chaque Skype pour le rôle de serveur d’entreprise qui a été déployé et mis en ligne. 
    
6. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Activer les utilisateurs**. 
    
7. Dans la page **Nouvelle Skype pour l’utilisateur Business Server** , cliquez sur **Ajouter**.
    
8. Pour définir les paramètres de recherche des objets que vous souhaitez trouver, sur la page **Sélectionner à partir d’Active Directory**, vous pouvez sélectionner **Rechercher**, puis éventuellement cliquer sur **Ajouter un filtre**. Vous pouvez également sélectionner **Recherche LDAP** et entrer une expression LDAP pour filtrer ou limiter les objets qui seront renvoyés. Une fois que vous avez défini vos options de recherche, cliquez sur **Rechercher**.
    
9. Dans le volet de résultats, sélectionnez les utilisateurs que vous souhaitez ajouter, puis cliquez sur **OK**.
    
10. Dans la page **Nouvelle Skype pour l’utilisateur Business Server** , les utilisateurs sélectionnés sont dans l’affichage des **utilisateurs** . In the **Assign users to a pool** list, select the server where the users should reside.
    
    Voici ci-après une liste des options pouvant être utilisées pour configurer les objets.
    
    - **Générer l’URI SIP de l’utilisateur**
    
    - **Téléphonie**
    
    - **URI de ligne**
    
    - **Stratégie de conférence**
    
    - **Stratégie de version du client**
    
    - **Stratégie de code confidentiel**
    
    - **Stratégie d’accès externe**
    
    - **Stratégie d’archivage**
    
    - **Stratégie d’emplacement**
    
    - **Stratégie du client**
    
    Pour tester la fonctionnalité de base, sélectionnez l’option que vous préférez pour le paramètre **URI SIP de l’utilisateur de générer** (autres options Paramètres de configuration utilisés par défaut), puis cliquez sur **Activer**, comme illustré dans la figure.
    
     ![Activez des utilisateurs dans le Panneau de configuration.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Une page récapitulative s’affiche. Elle contient une coche dans la colonne **Activé** pour indiquer que les utilisateurs sont configurés. La colonne **Adresse SIP** affiche l’adresse dont vous avez besoin pour configurer la connexion de l’utilisateur.
    
     ![Utilisateurs ajoutés au Panneau de configuration de Skype Entreprise Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Connectez un utilisateur sur un ordinateur lié au domaine et un autre utilisateur sur un autre ordinateur du domaine.
    
13. Installer Skype pour Business client sur chacun des deux ordinateurs clients, puis vérifiez que les deux utilisateurs peuvent se connecter à Skype pour Business Server et peuvent envoyer des messages instantanés entre eux.
    

