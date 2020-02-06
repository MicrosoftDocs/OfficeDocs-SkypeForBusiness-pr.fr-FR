---
title: Créer un pool d’objets dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Résumé : créer un pool de serveurs vidéo Interop dans Skype entreprise Server à l’aide du générateur de topologie.'
ms.openlocfilehash: 474752253312b58b87a3d01f445bd93eabdaf203
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798051"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Créer un pool d’objets dans Skype entreprise Server
 
**Résumé :** Créer un pool de serveurs Video Interop dans Skype entreprise Server à l’aide du générateur de topologie.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Création d’un VIS ou d’un pool de VIS à l’aide du Générateur de topologie

1. Ouvrez le Générateur de topologie sur le serveur frontal. Dans le volet gauche de la fenêtre du générateur de topologie, cliquez avec le bouton droit sur **pools de serveurs d’interopérabilité vidéo** et sélectionnez **nouvelle liste de serveurs d’interopérabilité vidéo**. 
    
2. Cela a pour effet d’ouvrir l’assistant **Créer un nouveau pool de serveurs d’interopérabilité vidéo**. Fournissez le nom de domaine complet du pool pour le nouveau serveur d’interopérabilité vidéo, puis sélectionnez **ce pool possède un serveur** ou **ce pool a plusieurs serveurs** en fonction de votre configuration requise, puis appuyez sur **suivant**.
    
    Si vous voulez déployer un pool de serveurs d’interopérabilité vidéo pour garantir une disponibilité élevée, sélectionnez **ce pool possède plusieurs serveurs**. Avec cette option, n’oubliez pas que : 
    
    - Vous devez déployer l’équilibrage de charge DNS pour prendre en charge les pools de serveurs Video Interop. 
    
   - Sur la page suivante, pour l’élément **Définir les ordinateurs dans ce pool**, entrez le **nom de domaine complet de l’ordinateur** pour chaque serveur du pool dans la zone de texte, puis cliquez sur **Ajouter**. Répétez cette étape pour ajouter un autre serveur d’interopérabilité vidéo au pool. Quand vous avez défini tous les ordinateurs du pool, appuyez sur **Suivant**.
    
     Si vous ne voulez déployer qu’un seul serveur Video Interop dans la liste, car vous n’avez pas besoin d’une haute disponibilité, sélectionnez **ce pool possède un serveur** , puis appuyez sur **suivant**.
    
3. Sélectionnez le pool du tronçon suivant/FE dans la liste déroulante et appuyez sur **Suivant**.
    
4. Sélectionnez un pool Edge à associer au VIS et appuyez sur **Terminer**.
    
5. Configurez un port TCP ou TLS.
    
    Sélectionnez le serveur vidéo d’interopérabilité que vous venez d’ajouter dans le volet gauche du générateur de topologie, cliquez avec le bouton droit sur celui-ci, puis sélectionnez **modifier les propriétés**. Activez ou mettez à jour le port TCP ou TLS selon vos besoins et choisissez **OK**. Même si le protocole TLS par défaut est ajouté, seul TCP a été entièrement testé avec Cisco Unified Communications Manager (CallManager ou CUCM).
    
6. Ajoutez une passerelle vidéo. Pour ce faire, développez les composants partagés, cliquez avec le bouton droit sur **Passerelles vidéo** et sélectionnez **Nouvelle passerelle vidéo**.
    
7. Indiquez le nom de domaine complet ou l’adresse IP de la passerelle vidéo. La passerelle vidéo peut se trouver dans un sous-domaine ou dans un domaine différent. Le CUCM utilisé par les VTC de votre système sert de passerelle vidéo.
    
8. Sélectionnez IPv4 ou IPv6 selon la situation. Vous pouvez utiliser toutes les adresses IP configurées ou limiter l’utilisation du service à certaines adresses IP.
    
9. Sélectionnez le port d’écoute de la passerelle vidéo. Sélectionnez le protocole de transport (TCP ou TLS) et associez-le à un serveur d’interopérabilité vidéo configuré pour une ligne SIP vidéo. Le protocole de transport pour la passerelle vidéo doit correspondre au protocole de transport configuré pour le VIS.
    
10. Une jonction vidéo SIP correspondante est ajoutée une fois que l’étape ci-dessus a été effectuée. Cliquez avec le bouton droit sur la jonction vidéo SIP et sélectionnez la jonction qui vient d’être ajoutée. Le nom du Trunk SIP vidéo, le serveur d’interopérabilité vidéo associé, le protocole de transport SIP et le port peuvent tous être modifiés. 
    
    > [!NOTE]
    >  Un serveur Video Interop prend en charge 1 : N Trunks. De ce fait, il est possible d’ajouter plusieurs Trunks, qui sont associés à un serveur d’interopérabilité vidéo unique, où chaque Trunk est arrêté sur une autre passerelle vidéo. La limitation réside dans le fait qu’une passerelle vidéo particulière dispose d’une seule ligne et qu’elle peut être définie pour le déploiement de Skype entreprise Server.
  
11. Publiez le document topologique comme décrit dans la rubrique [créer et publier une nouvelle topologie dans Skype entreprise Server 2015](../../deploy/install/create-and-publish-new-topology.md).
    
    > [!NOTE]
    > Pour améliorer la résilience, il est possible que vous souhaitiez configurer un deuxième serveur de technologie d’interopérabilité vidéo ou un pool frontal de sauvegarde. Pour obtenir des renseignements complémentaires, veuillez consulter la rubrique [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency).
  
Toutes les tâches exécutées à l’aide du Générateur de topologie sont maintenant terminées. Installez maintenant le logiciel sur le ou les nouveaux serveurs VIS.
## <a name="see-also"></a>Voir aussi

[Déploiement du rôle serveur sur Skype entreprise Server](deploy-the-vis-server-role.md)

[Planifier le serveur Video Interop dans Skype entreprise Server](../../plan-your-deployment/video-interop-server.md)
  
[Création et publication d’une topologie dans Skype Entreprise Server 2015](../../deploy/install/create-and-publish-new-topology.md)
