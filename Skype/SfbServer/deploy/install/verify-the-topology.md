---
title: Vérifier la topologie dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Résumé : Découvrez comment vérifier que la topologie Skype Entreprise Server et les serveurs Active Directory fonctionnent comme prévu. Téléchargez une version d’évaluation gratuite de Skype Entreprise Server à partir du Centre d’évaluation Microsoft à l’adresse : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server'
ms.openlocfilehash: 0c2307f3ad0416a7175d92a1440744dbda9b31d3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833834"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Vérifier la topologie dans Skype Entreprise Server
 
**Résumé :** Découvrez comment vérifier que la topologie Skype Entreprise Server et les serveurs Active Directory fonctionnent comme prévu. Téléchargez une version d’évaluation gratuite de Skype Entreprise Server à partir du [Centre d’évaluation Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Une fois la topologie publiée et les composants du système Skype Entreprise Server installés sur chacun des serveurs de la topologie, vous êtes prêt à vérifier que la topologie fonctionne comme prévu. Cela inclut la vérification que la configuration s’est propagée à tous les serveurs Active Directory afin que l’ensemble du domaine sache que Skype Entreprise est disponible dans le domaine. Vous pouvez suivre les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez suivre les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5, comme indiqué dans le diagramme. La vérification de la topologie est l’étape 8 sur 8.
  
![Diagramme de vue d’ensemble.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Tester le déploiement de pool frontal

La dernière étape consiste à tester le pool frontal et à vérifier que les clients Skype Entreprise peuvent communiquer entre eux. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Ajouter des utilisateurs et vérifier la connectivité du client

1. Utilisez les ordinateurs et les utilisateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle d’administrateur pour le déploiement de Skype Entreprise Server (sur lequel le Panneau de contrôle Skype Entreprise Server est installé) au groupe **CSAdministrator.**
    
    > [!IMPORTANT]
    > Si vous n’ajoutez pas les utilisateurs et groupes appropriés au groupe CsAdministors, vous recevrez une erreur lorsque vous ouvrirez le Panneau de contrôle Skype Entreprise Server, qui indique « Non autorisé : l’accès est refusé en raison d’un échec d’autorisation du contrôle d’accès basé sur un rôle (RBAC). » 
  
2. Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.
    
    > [!NOTE]
    > Le compte d’utilisateur ne peut pas être l’administrateur local d’un serveur exécutant Skype Entreprise Server. 
  
3. Utilisez le compte d’administration pour vous connecter à l’ordinateur sur lequel le Panneau de contrôle Skype Entreprise Server est installé.
    
4. Démarrez le Panneau de contrôle Skype Entreprise Server, puis fournissez les informations d’identification, si vous y êtes invité. Le Panneau de contrôle Skype Entreprise Server affiche les informations de déploiement.
    
5. Dans la barre de navigation de gauche, cliquez sur Topologie, puis vérifiez que l’état du service affiche un ordinateur avec une flèche verte et qu’une coche verte pour l’état de la réplication est en regard de chaque rôle Skype Entreprise Server qui a été déployé et mis en ligne. 
    
6. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Activer les utilisateurs**. 
    
7. Dans la page **Nouvel utilisateur Skype Entreprise Server,** cliquez sur **Ajouter.**
    
8. Pour définir les paramètres de recherche des objets que vous souhaitez trouver, sur la page **Sélectionner à partir d’Active Directory**, vous pouvez sélectionner **Rechercher**, puis éventuellement cliquer sur **Ajouter un filtre**. Vous pouvez également sélectionner **Recherche LDAP** et entrer une expression LDAP pour filtrer ou limiter les objets qui seront renvoyés. Une fois que vous avez choisi vos options de recherche, cliquez sur **Rechercher.**
    
9. Dans le volet Résultats de la recherche, sélectionnez les utilisateurs que vous souhaitez ajouter, puis cliquez sur **OK.**
    
10. Dans la page **Nouvel utilisateur Skype Entreprise Server,** les utilisateurs que vous avez sélectionnés sont affichés dans **l’affichage** Utilisateurs. Dans la **liste Affecter des utilisateurs à un pool,** sélectionnez le serveur où les utilisateurs doivent résider.
    
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
    
    Pour tester les fonctionnalités de base, sélectionnez l’option de votre choix pour le paramètre Générer **l’URI SIP de l’utilisateur** (les autres options de la configuration utilisent les paramètres par défaut), puis cliquez sur **Activer,** comme illustré dans la figure.
    
     ![Activez les utilisateurs dans le Panneau de contrôle.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Une page récapitulatif s’affiche et affiche une coche dans la colonne **Enabled** pour indiquer que les utilisateurs sont en cours d’installation. La **colonne d’adresse SIP** affiche l’adresse dont vous avez besoin pour la configuration de la connectez-vous de l’utilisateur.
    
     ![Utilisateurs ajoutés au Panneau de contrôle Skype Entreprise Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Connectez un utilisateur à un ordinateur qui est joint au domaine et un autre utilisateur sur un autre ordinateur du domaine.
    
13. Installez le client Skype Entreprise sur chacun des deux ordinateurs clients, puis vérifiez que les deux utilisateurs peuvent se connecter à Skype Entreprise Server et s’envoyer des messages instantanés entre eux.
    

