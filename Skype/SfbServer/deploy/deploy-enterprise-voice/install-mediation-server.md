---
title: Installation des fichiers du serveur de médiation dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Résumé : Apprenez à installer les fichiers de serveur de médiation dans Skype pour Business Server 2015.'
ms.openlocfilehash: 8b7b68142c180ee1b06963afbb1b7a9ca6d4319c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server-2015"></a>Installation des fichiers du serveur de médiation dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à installer les fichiers de serveur de médiation dans Skype pour Business Server 2015.
  
Pour mener à bien cette procédure, vous devez être connecté au serveur au minimum en tant qu’administrateur local et utilisateur de domaine appartenant au moins au groupe RTCUniversalReadOnlyAdmins.
  
Procédez comme indiqué dans cette rubrique pour exécuter Skype pour l’Assistant de déploiement Business Server installer les fichiers de serveur de médiation sur un ordinateur que vous avez ajoutés à un pool de serveur de médiation après avoir utilisé le Générateur de topologies à définir et à publier le pool. Lorsque vous installez les fichiers de serveur de médiation, vous également installez et assignez le certificat requis par chaque ordinateur dans un pool de serveur de médiation. 
  
> [!NOTE]
> Cette rubrique suppose que vous avez déjà défini et publié un pool de serveur de médiation autonome dans votre topologie, comme décrit dans le [déploiement d’un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server 2015](deploy-a-mediation-server.md). 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Pour installer les fichiers sur un pool de serveurs de médiation autonome

1. Le support d’installation, cliquez sur _ \<support d’installation de\> _ **\Setup\amd64\Setup.exe**, puis cliquez sur **Exécuter en tant qu’administrateur**.
    
2. Dans la page **Emplacement d’installation**, cliquez sur **OK**.
    
3. Dans la page **Contrat de Licence Utilisateur Final**, cliquez sur **J’accepte**, puis sur **OK**. (Cette étape est nécessaire pour continuer.)
    
4. Sur la page **Skype pour l’Assistant de déploiement de Business Server** , cliquez sur **installation ou mise à jour des Skype pour système de serveur d’entreprise**.
    
5. Lors de l’**étape 1 : installation du magasin de configuration local**, cliquez sur **Exécuter**, puis suivez les instructions affichées à l’écran.
    
6. Dans la page **Configurer un réplica local du magasin central de gestion**, acceptez le paramètre par défaut **Récupérer directement à partir du magasin central de gestion**, puis cliquez sur **Suivant**.
    
7. Dans la page **Exécution de commandes**, lorsque le statut de la tâche est **Terminé**, cliquez sur **Terminer**.
    
8. Regard **étape 2 : installation ou suppression de Skype pour les composants du serveur Business**et cliquez sur **exécuter**, puis cliquez sur **suivant**.
    
9. Dans la page **Exécution de commandes**, lorsque le statut de la tâche est **Terminé**, cliquez sur **Terminer**.
    
10. Lors de l’**étape 3 : demande, installation et affectation des certificats**, cliquez sur **Exécuter**. Suivez les instructions qui s’affichent à l’écran, en acceptant les paramètres par défaut. Le serveur de médiation nécessite un certificat. Vous devrez donc répéter deux fois l’**étape 3** : une fois pour émettre le certificat nécessaire, une autre pour l’affecter.
    
11. Une fois le certificat émis et attribué lors de l’**étape 4: démarrage des services**, cliquez sur **Exécuter**, puis suivez les instructions affichées à l’écran.
    
12. Une fois l’**étape 4** terminée, redémarrez le serveur et connectez-vous y en tant que membre du groupe DomainAdmins.
    
13. Sur l’ordinateur où vous exécutez Skype pour Business Server du Panneau de configuration, vérifiez sur la page de **la topologie** de Skype pour entreprise panneau Server que le service du serveur de médiation est affiché sous la forme d’une coche verte. Si une croix rouge est affichée, sélectionnez le serveur de médiation. Dans le menu **Action**, cliquez sur **Démarrer tous les services**. 
    
Si vous avez ajouté plusieurs ordinateurs au pool de serveur de médiation, effectuez les étapes de cette procédure sur tous les autres ordinateurs dans le pool de serveur de médiation. Si vous n’avez pas besoin d’installer les fichiers de serveur de médiation pour tous les autres ordinateurs, puis suivez les procédures décrites dans [configuration troncs dans Skype pour Business Server 2015](configure-trunks.md) pour configurer les paramètres pour la connexion de jonction entre ce pool de serveur de médiation (ou toutes les Serveurs de médiation dans un site) et son homologue.

