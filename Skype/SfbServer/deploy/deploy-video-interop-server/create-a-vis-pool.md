---
title: Création d’un pool de serveurs d’interopérabilité vidéo (VIS) dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Résumé : Créer un pool de serveurs d’interopérabilité vidéo dans Skype pour 2015 de serveur d’entreprise à l’aide du Générateur de topologies.'
ms.openlocfilehash: ab34cf5b547301314bf169b56481818f78e9908a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-vis-pool-in-skype-for-business-server-2015"></a>Création d’un pool de serveurs d’interopérabilité vidéo (VIS) dans Skype Entreprise Server 2015
 
**Résumé :** Créer un pool de serveurs d’interopérabilité vidéo dans Skype pour 2015 de serveur d’entreprise à l’aide du Générateur de topologies.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Création d’un VIS ou d’un pool de VIS à l’aide du Générateur de topologie

1. Ouvrez le Générateur de topologie sur le serveur frontal. Dans le volet gauche du Générateur de topologies, cliquez droit sur ** Pools de serveur vidéo Interop ** et choisissez **Nouveau Pool de serveur vidéo Interop**. 
    
2. Cela a pour effet d’ouvrir l’assistant **Créer un nouveau pool de serveurs d’interopérabilité vidéo**. Fournir le nom FQDN du Pool pour le nouveau serveur d’interopérabilité vidéo et sélectionnez **ce pool possède un seul serveur** ou **ce pool possède plusieurs serveurs** en fonction de vos besoins, puis cliquez sur **suivant**.
    
    Si vous souhaitez déployer un pool de serveurs d’interopérabilité de vidéo pour offrir une haute disponibilité, sélectionnez **ce pool possède plusieurs serveurs**. Avec cette option, n’oubliez pas que : 
    
    - Vous devez déployer l’équilibrage de charge DNS pour prendre en charge les pools de serveurs d’interopérabilité vidéo. 
    
   - Sur la page suivante, pour l’élément **Définir les ordinateurs dans ce pool**, entrez le **nom de domaine complet de l’ordinateur** pour chaque serveur du pool dans la zone de texte, puis cliquez sur **Ajouter**. Répétez cette étape pour ajouter un autre serveur d’interopérabilité vidéo au pool. Quand vous avez défini tous les ordinateurs du pool, appuyez sur **Suivant**.
    
    Si vous souhaitez ne déployer qu’un seul serveur d’interopérabilité vidéo dans le pool, car vous n’avez pas besoin de haute disponibilité, sélectionnez **ce groupe dispose d’un serveur** puis cliquez sur **suivant**.
    
3. Sélectionnez le pool du tronçon suivant/FE dans la liste déroulante et appuyez sur **Suivant**.
    
4. Sélectionnez un pool Edge à associer au VIS et appuyez sur **Terminer**.
    
5. Configurez un port TCP ou TLS.
    
    Sélectionnez vidéo Interop serveur nouvellement ajouté à partir du volet de gauche du Générateur de topologies, avec le bouton droit dessus et sélectionnez **Modifier les propriétés**. Activez ou mettez à jour le port TCP ou TLS selon vos besoins et choisissez **OK**. Bien que TLS soit ajouté par défaut, seul le port TCP a été pleinement testé avec CUCM.
    
6. Ajoutez une passerelle vidéo. Pour ce faire, développez les composants partagés, cliquez avec le bouton droit sur **Passerelles vidéo** et sélectionnez **Nouvelle passerelle vidéo**.
    
7. Indiquez le nom de domaine complet ou l’adresse IP de la passerelle vidéo. La passerelle vidéo peut se trouver dans un sous-domaine ou dans un domaine différent. Le CUCM utilisé par les VTC de votre système sert de passerelle vidéo.
    
8. Sélectionnez IPv4 ou IPv6 selon la situation. Vous pouvez utiliser toutes les adresses IP configurées ou limiter l’utilisation du service à certaines adresses IP.
    
9. Sélectionnez le port d’écoute de la passerelle vidéo. Sélectionnez le protocole de Transport (TCP ou TLS) et l’associer à un serveur vidéo Interop est définie pour un vidéo SIP trunk. Le protocole de transport pour la passerelle vidéo doit correspondre au protocole de transport configuré pour le VIS.
    
10. Une jonction vidéo SIP correspondante est ajoutée une fois que l’étape ci-dessus a été effectuée. Cliquez avec le bouton droit sur la jonction vidéo SIP et sélectionnez la jonction qui vient d’être ajoutée. Le nom de jonction de SIP vidéo, associée à la vidéo serveur de protocole de Transport de SIP, Interop et port peut tous être modifié. 
    
    > [!NOTE]
    >  Un serveur d’interopérabilité vidéo prend en charge les puits 1 à n. Donc plusieurs troncs peuvent être ajoutés, qui sont associés à un seul serveur vidéo Interop, où chaque ligne se termine sur une passerelle vidéo différents. La limitation est qu’une passerelle vidéo tronc d’un seul et unique qui peut être définis pour le Skype pour le déploiement du serveur de l’entreprise.
  
11. Publier le Document de topologie, comme décrit dans [créer et publier la nouvelle topologie dans Skype pour Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).
    
    > [!NOTE]
    > Pour améliorer la souplesse, vous souhaiterez configurer un deuxième serveur d’interopérabilité vidéo ou de la VIS pool, ou une sauvegarde Front-End. Pour obtenir des renseignements complémentaires, veuillez consulter la rubrique [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency).
  
Toutes les tâches exécutées à l’aide du Générateur de topologie sont maintenant terminées. Installez maintenant le logiciel sur le ou les nouveaux serveurs VIS.
## <a name="see-also"></a>Voir aussi

#### 

[Déployer le rôle de serveur de VIS dans Skype pour Business Server 2015](deploy-the-vis-server-role.md)
#### 

[Plan pour un serveur interopérabilité vidéo dans Skype pour Business Server 2015](../../plan-your-deployment/video-interop-server.md)
  
[Créez et publiez la nouvelle topologie dans Skype pour Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)

