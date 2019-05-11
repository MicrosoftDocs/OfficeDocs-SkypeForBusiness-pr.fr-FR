---
title: Installer les fichiers pour le serveur de médiation dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Résumé : Découvrez comment installer les fichiers pour le serveur de médiation dans Skype pour Business Server.'
ms.openlocfilehash: 0f4428007f3506f0e3193d390441bf83301a47a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892327"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Installer les fichiers pour le serveur de médiation dans Skype pour Business Server
 
**Résumé :** Découvrez comment installer les fichiers pour le serveur de médiation dans Skype pour Business Server.
  
Pour mener à bien cette procédure, vous devez être connecté au serveur au minimum en tant qu’administrateur local et utilisateur de domaine appartenant au moins au groupe RTCUniversalReadOnlyAdmins.
  
Utilisez les étapes décrites dans cette rubrique pour exécuter les Skype pour l’Assistant de déploiement Business Server installer les fichiers pour le serveur de médiation sur un ordinateur que vous avez ajouté à un pool de serveur de médiation après avoir utilisé le Générateur de topologie pour définir et publier le pool. Lorsque vous installez les fichiers serveur de médiation, vous également installez et affectez le certificat requis par chaque ordinateur dans un pool de serveurs de médiation. 
  
> [!NOTE]
> Cette rubrique suppose que vous avez déjà défini et publié un pool de serveur de médiation autonome dans votre topologie, comme décrit dans [déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server](deploy-a-mediation-server.md). 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Pour installer les fichiers sur un pool de serveurs de médiation autonome

1. À partir du support d’installation, avec le bouton droit _ \<support d’installation\> _ **\Setup\amd64\Setup.exe**, puis cliquez sur **Exécuter en tant qu’administrateur**.
    
2. Dans la page **Emplacement d’installation**, cliquez sur **OK**.
    
3. Dans la page **Contrat de Licence Utilisateur Final**, cliquez sur **J’accepte**, puis sur **OK**. (Cette étape est nécessaire pour continuer.)
    
4. Dans la page **Skype pour l’Assistant de déploiement Business Server** , cliquez sur **installer ou mise à jour Skype pour le système de serveur d’entreprise**.
    
5. Lors de l’**étape 1 : installation du magasin de configuration local**, cliquez sur **Exécuter**, puis suivez les instructions affichées à l’écran.
    
6. Dans la page **Configurer un réplica local du magasin central de gestion**, acceptez le paramètre par défaut **Récupérer directement à partir du magasin central de gestion**, puis cliquez sur **Suivant**.
    
7. Dans la page **Exécution de commandes**, lorsque le statut de la tâche est **Terminé**, cliquez sur **Terminer**.
    
8. Regard **étape 2 : installer ou supprimer des Skype pour les composants du serveur Business**, cliquez sur **exécuter**, puis cliquez sur **suivant**.
    
9. Dans la page **Exécution de commandes**, lorsque le statut de la tâche est **Terminé**, cliquez sur **Terminer**.
    
10. Lors de l’**étape 3 : demande, installation et affectation des certificats**, cliquez sur **Exécuter**. Suivez les instructions qui s’affichent à l’écran, en acceptant les paramètres par défaut. Le serveur de médiation nécessite un certificat. Vous devrez donc répéter deux fois l’**étape 3** : une fois pour émettre le certificat nécessaire, une autre pour l’affecter.
    
11. Une fois le certificat émis et attribué lors de l’**étape 4: démarrage des services**, cliquez sur **Exécuter**, puis suivez les instructions affichées à l’écran.
    
12. Une fois l’**étape 4** terminée, redémarrez le serveur et connectez-vous y en tant que membre du groupe DomainAdmins.
    
13. Sur l’ordinateur sur lequel vous exécutez Skype pour Business Server le panneau de configuration, vérifiez sur la page **topologie** de Skype pour Business Server Control Panel l’état du service du serveur de médiation est affiché en tant qu’une coche verte. Si une croix rouge est affichée, sélectionnez le serveur de médiation. Dans le menu **Action**, cliquez sur **Démarrer tous les services**. 
    
Si vous avez ajouté plusieurs ordinateurs au pool de serveurs de médiation, effectuez les étapes de cette procédure sur tous les autres ordinateurs du pool de serveur de médiation. Si vous n’avez pas besoin installer les fichiers d’un serveur de médiation pour d’autres ordinateurs, puis suivez les procédures de [configuration de jonctions dans Skype pour Business Server](configure-trunks.md) pour configurer les paramètres pour la connexion de jonction entre ce pool de serveur de médiation (ou la médiation tous les Serveurs sur un site) et son homologue.

