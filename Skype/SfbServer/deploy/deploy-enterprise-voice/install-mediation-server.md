---
title: Installer les fichiers du serveur de médiation dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
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
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Résumé : Découvrez comment installer les fichiers pour le serveur de médiation dans Skype Entreprise Server.'
ms.openlocfilehash: 6efe52ab2964e8a9c95083bbcf6592573ebf7da2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839686"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Installer les fichiers du serveur de médiation dans Skype Entreprise Server
 
**Résumé :** Découvrez comment installer les fichiers pour le serveur de médiation dans Skype Entreprise Server.
  
Pour effectuer cette procédure, vous devez au minimum être connecté au serveur en tant qu’administrateur local et utilisateur de domaine membre au moins du groupe RTCUniversalReadOnlyAdmins.
  
Utilisez les étapes de cette rubrique pour exécuter l’Assistant Déploiement de Skype Entreprise Server pour installer les fichiers du serveur de médiation sur un ordinateur que vous avez ajouté à un pool de serveurs de médiation après avoir utilisé le Générateur de topologies pour définir et publier le pool. Lors de l’installation des fichiers du serveur de médiation, vous installez et affectez également le certificat requis par chaque ordinateur d’un pool de serveurs de médiation. 
  
> [!NOTE]
> Cette rubrique suppose que vous avez déjà défini et publié un pool de serveurs de médiation autonome dans votre topologie, comme décrit dans Déployer un serveur de médiation dans le Générateur de topologie dans [Skype Entreprise Server](deploy-a-mediation-server.md). 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Pour installer les fichiers d’un pool de serveurs de médiation autonome

1. Dans le support d’installation, cliquez avec le bouton\Setup\amd64\Setup.exe, puis cliquez _\<installation media\>_ **** sur Exécuter en **tant qu’administrateur.**
    
2. Dans la page **Emplacement de l’installation,** cliquez sur **OK.**
    
3. Dans la page **Contrat de licence** utilisateur final, cliquez sur **J’accepte,** puis sur **OK.** (Obligatoire pour continuer.)
    
4. Dans la page **Skype Entreprise Server’Assistant Déploiement,** cliquez sur Installer ou mettre **à jour Skype Entreprise Server système.**
    
5. À côté de **l’étape 1 : installer le magasin de configurations local,** cliquez sur **Exécuter,** puis suivez les instructions à l’écran.
    
6. Dans la page **Configurer le** réplica local du magasin central de gestion, acceptez la valeur par défaut Récupérer directement à partir du magasin **central** de gestion, puis cliquez sur **Suivant**.
    
7. Dans la page **Exécution de commandes,** lorsque l’état de la tâche s’affiche comme **Terminé,** cliquez sur **Terminer.**
    
8. À côté de **l’étape 2 :** installer ou supprimer Skype Entreprise Server composants, cliquez sur **Exécuter,** puis cliquez sur **Suivant**.
    
9. Dans la page **Exécution de commandes,** lorsque l’état de la tâche s’affiche comme **Terminé,** cliquez sur **Terminer.**
    
10. À côté de **l’étape 3 : Demander, installer ou affecter des certificats,** cliquez sur **Exécuter.** Suivez les instructions à l’écran, en acceptant les paramètres par défaut. Le serveur de médiation nécessite un certificat et vous exécutez donc l’étape **3** deux fois : une fois pour émettre le certificat requis et une autre pour l’affecter.
    
11. Lorsque le certificat a été émis et affecté correctement, à côté de l’étape **4**: Démarrer les services, cliquez sur **Exécuter,** puis suivez les instructions à l’écran.
    
12. Une **fois l’étape 4** terminée, redémarrez le serveur et connectez-vous au serveur en tant que membre du groupe DomainAdmins.
    
13. Sur l’ordinateur sur lequel vous exécutez le Panneau de Skype Entreprise Server, vérifiez dans la **page** Topologie du Panneau de Skype Entreprise Server que l’état du service du serveur de médiation s’affiche sous la main d’une coche verte. Si un X rouge apparaît à la place, sélectionnez le serveur de médiation. Dans le menu **Action,** cliquez **sur Démarrer tous les services.** 
    
Si vous avez ajouté plusieurs ordinateurs au pool de serveurs de médiation, effectuez les étapes de cette procédure sur tous les autres ordinateurs du pool de serveurs de médiation. Si vous n’avez pas besoin d’installer des fichiers pour le serveur de médiation pour d’autres [ordinateurs,](configure-trunks.md) suivez les procédures de la procédure de configuration des connexions dans Skype Entreprise Server pour configurer les paramètres de la connexion entre ce pool de serveurs de médiation (ou tous les serveurs de médiation d’un site) et son homologue.

