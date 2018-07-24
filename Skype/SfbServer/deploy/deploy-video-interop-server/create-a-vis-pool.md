---
title: Créer un pool VIS dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Résumé : Créez un pool de serveurs d’interopérabilité vidéo dans Skype pour Business Server à l’aide du Générateur de topologie.'
ms.openlocfilehash: f284163bc52f4e62c3ec5b1c7966f3c663ee09f7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978815"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Créer un pool VIS dans Skype pour Business Server
 
**Résumé :** Créer un pool de serveurs d’interopérabilité vidéo dans Skype pour Business Server à l’aide du Générateur de topologie.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Création d’un VIS ou d’un pool de VIS à l’aide du Générateur de topologie

1. Ouvrez le Générateur de topologie sur le serveur frontal. Dans le volet gauche du Générateur de topologie, cliquez avec le bouton droit sur **Pools de serveurs d’interopérabilité vidéo** et choisissez **Nouveau Pool de serveurs d’interopérabilité vidéo**. 
    
2. Cela a pour effet d’ouvrir l’assistant **Créer un nouveau pool de serveurs d’interopérabilité vidéo**. Fournir le nom complet du Pool pour le nouveau serveur d’interopérabilité vidéo et sélectionnez **ce pool possède un seul serveur** ou **ce pool possède plusieurs serveurs** en fonction de vos besoins, puis cliquez sur **suivant**.
    
    Si vous souhaitez déployer un pool de serveurs d’interopérabilité de vidéo pour fournir une haute disponibilité, sélectionnez **ce pool possède plusieurs serveurs**. Avec cette option, n’oubliez pas que : 
    
    - Vous devez déployer l’équilibrage de charge DNS pour prendre en charge les pools de serveurs d’interopérabilité vidéo. 
    
   - Sur la page suivante, pour l’élément **Définir les ordinateurs dans ce pool**, entrez le **nom de domaine complet de l’ordinateur** pour chaque serveur du pool dans la zone de texte, puis cliquez sur **Ajouter**. Répétez cette étape pour ajouter un autre serveur d’interopérabilité vidéo vers le pool. Quand vous avez défini tous les ordinateurs du pool, appuyez sur **Suivant**.
    
    Si vous souhaitez ne déployer qu’un seul serveur d’interopérabilité vidéo dans le pool, car vous n’avez pas besoin de haute disponibilité, sélectionnez **ce pool possède un seul serveur** , puis cliquez sur **suivant**.
    
3. Sélectionnez le pool du tronçon suivant/FE dans la liste déroulante et appuyez sur **Suivant**.
    
4. Sélectionnez un pool Edge à associer au VIS et appuyez sur **Terminer**.
    
5. Configurez un port TCP ou TLS.
    
    Sélectionnez le serveur d’interopérabilité vidéo nouvellement ajoutés dans le volet gauche du Générateur de topologie, avec le bouton droit dessus et sélectionnez **Modifier les propriétés**. Activez ou mettez à jour le port TCP ou TLS selon vos besoins et choisissez **OK**. Bien que TLS est ajouté par défaut, seul TCP a été intégralement testé avec Cisco Unified Communications Manager (CallManager ou CUCM).
    
6. Ajoutez une passerelle vidéo. Pour ce faire, développez les composants partagés, cliquez avec le bouton droit sur **Passerelles vidéo** et sélectionnez **Nouvelle passerelle vidéo**.
    
7. Indiquez le nom de domaine complet ou l’adresse IP de la passerelle vidéo. La passerelle vidéo peut se trouver dans un sous-domaine ou dans un domaine différent. Le CUCM utilisé par les VTC de votre système sert de passerelle vidéo.
    
8. Sélectionnez IPv4 ou IPv6 selon la situation. Vous pouvez utiliser toutes les adresses IP configurées ou limiter l’utilisation du service à certaines adresses IP.
    
9. Sélectionnez le port d’écoute de la passerelle vidéo. Sélectionnez le protocole de Transport (TCP ou TLS) et l’associer à un serveur d’interopérabilité vidéo qui est définie pour une jonction SIP vidéo. Le protocole de transport pour la passerelle vidéo doit correspondre au protocole de transport configuré pour le VIS.
    
10. Une jonction vidéo SIP correspondante est ajoutée une fois que l’étape ci-dessus a été effectuée. Cliquez avec le bouton droit sur la jonction vidéo SIP et sélectionnez la jonction qui vient d’être ajoutée. Le nom de jonction SIP vidéo, associée à la vidéo serveur de protocole de Transport SIP, interopérabilité et port est possible de modifier. 
    
    > [!NOTE]
    >  Un serveur d’interopérabilité vidéo prend en charge des jonctions 1 : n. Par conséquent, plusieurs jonctions peuvent être ajoutées, qui sont associé à un seul serveur vidéo Interop, où chaque jonction s’arrête sur une passerelle vidéo différents. La limite est qu’une passerelle vidéo particulier qu’une seule jonction qui peut être définies pour le Skype pour le déploiement de serveur d’entreprise.
  
11. Publier le Document de topologie, comme décrit dans [créer et publier la nouvelle topologie dans Skype pour Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).
    
    > [!NOTE]
    > Pour améliorer la résistance, vous souhaiterez peut-être configurer un pool de serveur d’interopérabilité vidéo ou VIS deuxième ou un pool frontal de sauvegarde. Pour obtenir des renseignements complémentaires, veuillez consulter la rubrique [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency).
  
Toutes les tâches exécutées à l’aide du Générateur de topologie sont maintenant terminées. Installez maintenant le logiciel sur le ou les nouveaux serveurs VIS.
## <a name="see-also"></a>Voir aussi

[Déployer le rôle de serveur VIS Skype pour Business Server](deploy-the-vis-server-role.md)

[Planification de serveur interopérabilité vidéo dans Skype Business Server](../../plan-your-deployment/video-interop-server.md)
  
[Création et publication d’une topologie dans Skype Entreprise Server 2015](../../deploy/install/create-and-publish-new-topology.md)