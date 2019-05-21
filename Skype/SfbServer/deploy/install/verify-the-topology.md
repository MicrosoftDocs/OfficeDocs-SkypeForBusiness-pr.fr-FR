---
title: Vérifier la topologie dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Résumé: Découvrez comment vérifier que la topologie du serveur Skype entreprise et les serveurs Active Directory fonctionnent comme prévu. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft pour:.'
ms.openlocfilehash: aad91c7bfb1e3187ace5d5caec4e3f18952a11d8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306590"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Vérifier la topologie dans Skype entreprise Server
 
**Résumé:** Découvrez comment vérifier que la topologie de Skype entreprise Server et les serveurs Active Directory fonctionnent comme prévu. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du [Centre d’évaluation Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Après la publication de la topologie et des composants du système Skype entreprise Server installés sur chacun des serveurs de la topologie, vous êtes prêt à vérifier que la topologie fonctionne correctement. Pour cela, vous devez vérifier que la configuration a été propagée sur tous les serveurs Active Directory de sorte que l’intégralité du domaine sache que Skype entreprise est disponible dans le domaine. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Cependant, vous devez réaliser les étapes 6, 7 et 8 dans l’ordre stipulé, après les étapes 1 à 5, comme indiqué dans le diagramme. La vérification de la topologie est la 8e des 8 étapes.
  
![Schéma de vue d’ensemble.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Test du déploiement de pool frontal

La dernière étape consiste à tester le pool frontal et à confirmer que les clients Skype entreprise peuvent communiquer entre eux. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Ajout d’utilisateur et vérification de la connectivité entre les clients

1. Utilisez les ordinateurs et les utilisateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle administrateur pour le déploiement de Skype entreprise Server (sur lequel est installé le panneau de configuration Skype entreprise Server) vers le groupe **CSAdministrator** .
    
    > [!IMPORTANT]
    > Si vous n’ajoutez pas les utilisateurs et les groupes appropriés au groupe CsAdministors, vous recevez un message d’erreur lors de l’ouverture du panneau de configuration Skype entreprise Server qui lit «non autorisé: accès refusé en raison d’un échec de l’autorisation de contrôle d’accès basé sur un rôle (RBAC) ." 
  
2. Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.
    
    > [!NOTE]
    > Le compte d’utilisateur ne peut pas être l’administrateur local de tout serveur exécutant Skype entreprise Server. 
  
3. Utilisez le compte administratif pour vous connecter à l’ordinateur sur lequel est installé le panneau de configuration Skype entreprise Server.
    
4. Démarrez le panneau de configuration Skype entreprise Server, puis fournissez les informations d’identification, le cas échéant. Le panneau de configuration Skype entreprise Server affiche des informations de déploiement.
    
5. Dans la barre de navigation de gauche, cliquez sur **Topology**, puis vérifiez que l’état du service affiche un ordinateur avec une flèche verte et qu’une coche verte pour l’état de la réplication est située en regard de chaque rôle serveur Skype entreprise déployé et remis en ligne. 
    
6. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Activer les utilisateurs**. 
    
7. Dans la page de l' **utilisateur Skype entreprise Server** , cliquez sur **Ajouter**.
    
8. Pour définir les paramètres de recherche des objets que vous souhaitez trouver, sur la page **Sélectionner à partir d’Active Directory**, vous pouvez sélectionner **Rechercher**, puis éventuellement cliquer sur **Ajouter un filtre**. Vous pouvez également sélectionner **Recherche LDAP** et entrer une expression LDAP pour filtrer ou limiter les objets qui seront renvoyés. Une fois que vous avez défini vos options de recherche, cliquez sur **Rechercher**.
    
9. Dans le volet de résultats, sélectionnez les utilisateurs que vous souhaitez ajouter, puis cliquez sur **OK**.
    
10. Dans la page de l' **utilisateur de Skype entreprise Server** , les utilisateurs sélectionnés se trouvent dans l’affichage **utilisateurs** . In the **Assign users to a pool** list, select the server where the users should reside.
    
    Voici ci-après une liste des options pouvant être utilisées pour configurer les objets.
    
    - **Générer URI SIP de l’utilisateur**
    
    - **Téléphonie**
    
    - **URI de ligne**
    
    - **Stratégie de conférence**
    
    - **Stratégie de version du client**
    
    - **Stratégie de code confidentiel**
    
    - **Stratégie d’accès externe**
    
    - **Stratégie d’archivage**
    
    - **Stratégie d’emplacement**
    
    - **Stratégie du client**
    
    Pour tester la fonctionnalité de base, sélectionnez l’option de votre choix pour le paramètre **URI SIP de l’utilisateur générer** (les autres options dans la configuration utiliser les paramètres par défaut), puis cliquez sur **activer**, comme indiqué dans l’illustration.
    
     ![Activez des utilisateurs dans le Panneau de configuration.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Une page récapitulative s’affiche. Elle contient une coche dans la colonne **Activé** pour indiquer que les utilisateurs sont configurés. La colonne **Adresse SIP** affiche l’adresse dont vous avez besoin pour configurer la connexion de l’utilisateur.
    
     ![Utilisateurs ajoutés au Panneau de configuration de Skype Entreprise Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Connectez un utilisateur sur un ordinateur lié au domaine et un autre utilisateur sur un autre ordinateur du domaine.
    
13. Installez le client Skype entreprise sur chacun des deux ordinateurs client, puis vérifiez que les deux utilisateurs peuvent se connecter à Skype entreprise Server et pouvoir vous envoyer des messages instantanés.
    

