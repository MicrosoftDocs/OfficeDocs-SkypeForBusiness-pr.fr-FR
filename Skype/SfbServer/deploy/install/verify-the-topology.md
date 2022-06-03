---
title: Vérifier la topologie dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Résumé : Découvrez comment vérifier que la topologie Skype Entreprise Server et les serveurs Active Directory fonctionnent comme prévu.'
ms.openlocfilehash: ec63977f4c70845f39aafe3521591ec93777f7d5
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860545"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Vérifier la topologie dans Skype Entreprise Server
 
**Résumé:** Découvrez comment vérifier que la topologie Skype Entreprise Server et les serveurs Active Directory fonctionnent comme prévu.
  
Une fois la topologie publiée et les composants système Skype Entreprise Server installés sur chacun des serveurs de la topologie, vous êtes prêt à vérifier que la topologie fonctionne comme prévu. Cela inclut la vérification que la configuration s’est propagée à tous les serveurs Active Directory afin que l’ensemble du domaine sache Skype Entreprise est disponible dans le domaine. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez effectuer les étapes 6, 7 et 8 dans l’ordre, et après les étapes 1 à 5, comme indiqué dans le diagramme. La vérification de la topologie est l’étape 8 sur 8.
  
![Diagramme de vue d’ensemble.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Tester le déploiement du pool frontal

La dernière étape consiste à tester le pool frontal et à confirmer que Skype Entreprise clients peuvent communiquer entre elles. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Ajouter des utilisateurs et vérifier la connectivité du client

1. Utilisez les ordinateurs et utilisateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle d’administrateur pour le déploiement Skype Entreprise Server (sur lequel Skype Entreprise Server Panneau de configuration est installé) au groupe **CSAdministrator**.
    
    > [!IMPORTANT]
    > Si vous n’ajoutez pas les utilisateurs et groupes appropriés au groupe CsAdministors, une erreur s’affiche lorsque vous ouvrez Skype Entreprise Server Panneau de configuration indiquant « Non autorisé : l’accès est refusé en raison d’une défaillance du contrôle d’accès en fonction du rôle (RBAC). » 
  
2. Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.
    
    > [!NOTE]
    > Le compte d’utilisateur ne peut pas être l’administrateur local d’un serveur exécutant Skype Entreprise Server. 
  
3. Utilisez le compte d’administration pour vous connecter à l’ordinateur sur lequel Skype Entreprise Server Panneau de configuration est installé.
    
4. Démarrez Skype Entreprise Server Panneau de configuration, puis fournissez des informations d’identification, si vous y êtes invité. Skype Entreprise Server Panneau de configuration affiche les informations de déploiement.
    
5. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis vérifiez que l’état du service affiche un ordinateur avec une flèche verte et qu’une coche verte pour l’état de réplication est en regard de chaque rôle Skype Entreprise Server qui a été déployé et mis en ligne. 
    
6. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Activer les utilisateurs**. 
    
7. Dans la page **Nouvel utilisateur Skype Entreprise Server**, cliquez sur **Ajouter**.
    
8. Pour définir les paramètres de recherche des objets que vous souhaitez trouver, sur la page **Sélectionner à partir d’Active Directory**, vous pouvez sélectionner **Rechercher**, puis éventuellement cliquer sur **Ajouter un filtre**. Vous pouvez également sélectionner **Recherche LDAP** et entrer une expression LDAP pour filtrer ou limiter les objets qui seront renvoyés. Une fois que vous avez choisi vos options de recherche, cliquez sur **Rechercher**.
    
9. Dans le volet Résultats de la recherche, sélectionnez les utilisateurs que vous souhaitez ajouter, puis cliquez sur **OK**.
    
10. Dans la page **Nouvel utilisateur Skype Entreprise Server**, les utilisateurs que vous avez sélectionnés figurent dans l’affichage **Utilisateurs**. Dans la liste **Affecter des utilisateurs à un pool** , sélectionnez le serveur où les utilisateurs doivent résider.
    
    Voici une liste d’options que vous pouvez utiliser pour configurer les objets.
    
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
    
    Pour tester les fonctionnalités de base, sélectionnez l’option que vous préférez pour le paramètre **d’URI SIP de l’utilisateur Generate** (les autres options de la configuration utilisent les paramètres par défaut), puis cliquez sur **Activer**, comme illustré dans la figure.
    
     ![Activez les utilisateurs dans Panneau de configuration.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Une page récapitulative s’affiche et affiche une coche dans la colonne **Activé** pour indiquer que les utilisateurs sont configurés. La colonne **d’adresse SIP** affiche l’adresse dont vous avez besoin pour la configuration de connexion utilisateur.
    
     ![Utilisateurs ajoutés à Skype Entreprise Server Panneau de configuration.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Connectez un utilisateur à un ordinateur joint au domaine et un autre utilisateur à un autre ordinateur du domaine.
    
13. Installez Skype Entreprise client sur chacun des deux ordinateurs clients, puis vérifiez que les deux utilisateurs peuvent se connecter à Skype Entreprise Server et peuvent s’envoyer des messages instantanés.
    

