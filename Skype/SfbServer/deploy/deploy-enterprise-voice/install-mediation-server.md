---
title: Installer les fichiers du serveur de médiation dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Résumé: Découvrez comment installer les fichiers du serveur de médiation dans Skype entreprise Server.'
ms.openlocfilehash: b73832586ba4a09cc51f67bddcaf30c2f85fcca1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240296"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Installer les fichiers du serveur de médiation dans Skype entreprise Server
 
**Résumé:** Découvrez comment installer les fichiers du serveur de médiation dans Skype entreprise Server.
  
Pour mener à bien cette procédure, vous devez être connecté au serveur au minimum en tant qu’administrateur local et utilisateur de domaine appartenant au moins au groupe RTCUniversalReadOnlyAdmins.
  
Suivez les étapes décrites dans cette rubrique pour exécuter l’Assistant Déploiement de Skype entreprise Server et installer les fichiers de médiation Server sur un ordinateur que vous avez ajouté à un pool de serveurs de médiation après avoir utilisé le générateur de topologie pour définir et publier le pool. Lors de l’installation de files Mediation Server, vous installez et attribuez également le certificat requis par chaque ordinateur d’un pool de serveurs de médiation. 
  
> [!NOTE]
> Cette rubrique part du principe que vous avez déjà défini et publié un pool de serveurs de médiation autonome dans votre topologie, comme décrit dans la rubrique [déploiement d’un serveur de médiation dans le générateur de topologie de Skype entreprise Server](deploy-a-mediation-server.md). 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Pour installer les fichiers sur un pool de serveurs de médiation autonome

1. Sur le support d’installation, cliquez avec le bouton droit sur _ \<installation Media\> _ **\Setup\amd64\Setup.exe**, puis cliquez sur **exécuter en tant qu’administrateur**.
    
2. Dans la page **Emplacement d’installation**, cliquez sur **OK**.
    
3. Dans la page **Contrat de Licence Utilisateur Final**, cliquez sur **J’accepte**, puis sur **OK**. (Cette étape est nécessaire pour continuer.)
    
4. Dans la page **Assistant Déploiement de Skype entreprise Server** , cliquez sur **installer ou mettre à jour le système Skype entreprise Server**.
    
5. Lors de l’**étape 1 : installation du magasin de configuration local**, cliquez sur **Exécuter**, puis suivez les instructions affichées à l’écran.
    
6. Dans la page **Configurer un réplica local du magasin central de gestion**, acceptez le paramètre par défaut **Récupérer directement à partir du magasin central de gestion**, puis cliquez sur **Suivant**.
    
7. Dans la page **Exécution de commandes**, lorsque le statut de la tâche est **Terminé**, cliquez sur **Terminer**.
    
8. À côté de l' **étape 2: configurer ou supprimer les composants serveur Skype entreprise**, cliquez sur **exécuter**, puis sur **suivant**.
    
9. Dans la page **Exécution de commandes**, lorsque le statut de la tâche est **Terminé**, cliquez sur **Terminer**.
    
10. Lors de l’**étape 3 : demande, installation et affectation des certificats**, cliquez sur **Exécuter**. Suivez les instructions qui s’affichent à l’écran, en acceptant les paramètres par défaut. Le serveur de médiation nécessite un certificat. Vous devrez donc répéter deux fois l’**étape 3** : une fois pour émettre le certificat nécessaire, une autre pour l’affecter.
    
11. Une fois le certificat émis et attribué lors de l’**étape 4: démarrage des services**, cliquez sur **Exécuter**, puis suivez les instructions affichées à l’écran.
    
12. Une fois l’**étape 4** terminée, redémarrez le serveur et connectez-vous y en tant que membre du groupe DomainAdmins.
    
13. Sur l’ordinateur sur lequel vous exécutez le panneau de configuration Skype entreprise Server, vérifiez sur la page **Topology** du panneau de configuration de Skype entreprise Server que l’état du service du serveur de médiation est représenté par une coche verte. Si une croix rouge est affichée, sélectionnez le serveur de médiation. Dans le menu **Action**, cliquez sur **Démarrer tous les services**. 
    
Si vous avez ajouté plusieurs ordinateurs au pool de serveurs de médiation, suivez les étapes de cette procédure sur tous les autres ordinateurs du pool de serveurs de médiation. Si vous n’avez pas besoin d’installer des fichiers pour un serveur de médiation pour d’autres ordinateurs, suivez les procédures décrites dans la section [configurer des Trunks dans Skype entreprise Server](configure-trunks.md) afin de configurer les paramètres de la connexion de Trunking entre ce pool de serveurs de médiation (ou toute la médiation). Serveurs sur un site) et son homologue.

