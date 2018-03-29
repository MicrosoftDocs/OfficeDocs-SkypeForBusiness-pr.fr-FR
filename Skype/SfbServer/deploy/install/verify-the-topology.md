---
title: Vérification de la topologie dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Résumé : Apprenez à vérifier le Skype pour la topologie du serveur de l’entreprise et les serveurs Active Directory fonctionnent comme prévu. Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 983ecf8b78a12898d18f04f7ec5c26c5271cf79a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="verify-the-topology-in-skype-for-business-server-2015"></a>Vérification de la topologie dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment vérifier la Skype pour la topologie du serveur de l’entreprise et les serveurs Active Directory fonctionnent comme prévu. Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise à partir du [Centre d’évaluation de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Une fois que la topologie de publication et le Skype pour les composants du système Business Server installé sur chacun des serveurs dans la topologie, vous êtes prêt à vérifier que la topologie fonctionne comme prévu. Cela inclut la vérification de la configuration s’est propagée à tous les serveurs Active Directory afin que l’intégralité du domaine sait que Skype pour entreprises est disponible dans le domaine. Vous pouvez effectuer les étapes 1 à 5 dans un ordre quelconque. Cependant, vous devez réaliser les étapes 6, 7 et 8 dans l’ordre stipulé, après les étapes 1 à 5, comme indiqué dans le diagramme. La vérification de la topologie est la 8e des 8 étapes.
  
![Schéma de vue d’ensemble.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Test du déploiement de pool frontal

La dernière étape consiste à tester le pool frontal et confirmer que Skype pour les clients d’entreprise peut communiquer entre eux. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Ajout d’utilisateur et vérification de la connectivité entre les clients

1. Utilisez utilisateurs et ordinateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle administrateur pour le Skype pour le déploiement de serveur d’entreprise (sur lequel est installé Skype pour panneau de contrôle serveur Business) au groupe **CSAdministrator** .
    
    > [!IMPORTANT]
    > Si vous n’ajoutez pas les utilisateurs et groupes appropriés au groupe CsAdministors, vous recevrez une erreur lorsque vous ouvrez Skype pour panneau de contrôle de serveur Business qui lit, « non autorisé : accès refusé en raison d’un échec de l’autorisation d’accès basé sur le rôle de contrôle (RBAC) ." 
  
2. Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.
    
    > [!NOTE]
    > Le compte d’utilisateur ne peut pas être l’administrateur local de n’importe quel serveur exécutant Skype pour Business Server. 
  
3. Utiliser le compte d’administrateur pour ouvrir une session sur l’ordinateur où est installé Skype pour le panneau de configuration de Business Server.
    
4. Démarrez Skype pour le panneau de configuration de Business Server et fournissent des informations d’identification, puis si vous y êtes invité. Skype pour le panneau de configuration de Business Server affiche des informations sur le déploiement.
    
5. Dans la barre de navigation de gauche, cliquez sur **la topologie**et confirmez que le statut du service indique un ordinateur avec une flèche verte et qu’une coche verte pour l’état de la réplication se trouve à côté de chaque Skype pour le rôle de serveur d’entreprise qui ont été déployé et mis en ligne. 
    
6. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Activer les utilisateurs**. 
    
7. Dans la page **Nouveau Skype pour l’utilisateur de serveur d’entreprise** , cliquez sur **Ajouter**.
    
8. Pour définir les paramètres de recherche des objets que vous souhaitez trouver, sur la page **Sélectionner à partir d’Active Directory**, vous pouvez sélectionner **Rechercher**, puis éventuellement cliquer sur **Ajouter un filtre**. Vous pouvez également sélectionner **Recherche LDAP** et entrer une expression LDAP pour filtrer ou limiter les objets qui seront renvoyés. Une fois que vous avez défini vos options de recherche, cliquez sur **Rechercher**.
    
9. Dans le volet de résultats, sélectionnez les utilisateurs que vous souhaitez ajouter, puis cliquez sur **OK**.
    
10. Dans la page **Nouveau Skype pour l’utilisateur de serveur d’entreprise** , les utilisateurs sélectionnés sont dans l’affichage des **utilisateurs** . Dans la liste **Attribuer des utilisateurs à un pool**, sélectionnez le serveur qui devrait héberger les utilisateurs.
    
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
    
    Pour tester la fonctionnalité de base, sélectionnez l’option que vous préférez pour le paramètre **d’URI SIP de l’utilisateur de générer** (les autres options dans la configuration par défaut d’utilisation), puis cliquez sur **Activer**, comme illustré dans la figure.
    
     ![Activez des utilisateurs dans le Panneau de configuration.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Une page récapitulative s’affiche. Elle contient une coche dans la colonne **Activé** pour indiquer que les utilisateurs sont configurés. La colonne **Adresse SIP** affiche l’adresse dont vous avez besoin pour configurer la connexion de l’utilisateur.
    
     ![Utilisateurs ajoutés au Panneau de configuration de Skype Entreprise Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Connectez un utilisateur sur un ordinateur lié au domaine et un autre utilisateur sur un autre ordinateur du domaine.
    
13. Installez Skype pour client d’entreprise sur chaque ordinateur deux client et puis vérifiez que les deux utilisateurs peuvent se connecter sur Skype pour Business Server et peuvent envoyer des messages instantanés à l’autre.
    

