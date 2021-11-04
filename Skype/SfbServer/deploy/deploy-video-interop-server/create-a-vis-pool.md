---
title: Créer un pool VIS dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Résumé : Créez un pool de serveurs d’interconnexion vidéo dans Skype Entreprise Server l’aide du Générateur de topologies.'
ms.openlocfilehash: e622c6510b23148617ad180ecc61480503a79a8a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748800"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Créer un pool VIS dans Skype Entreprise Server
 
**Résumé :** Créez un pool de serveurs d’interconnexion vidéo Skype Entreprise Server l’aide du Générateur de topologies.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Créer un vis ou un pool VIS à l’aide du Générateur de topologie

1. Ouvrez le Générateur de topologie sur le serveur frontal. Dans le volet gauche du Générateur de  topologies, cliquez avec le bouton droit sur pools de serveurs d’interop vidéo et choisissez Nouveau pool de serveurs **d’interop res vidéo.** 
    
2. Cela ouvre un Assistant Créer un nouveau pool de serveurs **d’interop vidéo.** Fournissez le nom de groupe du pool pour le nouveau serveur d’opation vidéo et sélectionnez soit ce **pool** possède un serveur, soit ce **pool** dispose de plusieurs serveurs en fonction de vos besoins, puis appuyez sur **Suivant**.
    
    Si vous souhaitez déployer un pool de serveurs d’interconnexion vidéo pour fournir une haute disponibilité, sélectionnez **Ce pool dispose de plusieurs serveurs.** Gardez à l’esprit cette option qui : 
    
    - Vous devez déployer l’équilibrage de charge DNS pour prendre en charge les pools de serveurs d’interconnexion vidéo. 
    
   - Dans la page suivante, pour définir les ordinateurs  de cet élément **de pool,** entrez le nom de domaine complet de chaque serveur du pool dans le champ de texte, puis cliquez sur **Ajouter**. Répétez cette étape pour ajouter un autre serveur d’opation vidéo au pool. Lorsque vous avez défini tous les ordinateurs du pool, appuyez sur **Suivant**.
    
     Si vous souhaitez déployer un seul serveur d’opation vidéo dans le pool, car vous n’avez pas besoin d’une haute disponibilité, sélectionnez Ce **pool** a un serveur et appuyez sur **Suivant**.
    
3. Sélectionnez le pool/fe du saut suivant dans la liste de listes et appuyez sur **Suivant.**
    
4. Sélectionnez un pool edge à associer au VIS, puis appuyez sur **Terminer.**
    
5. Définissez un port TCP ou TLS.
    
    Sélectionnez le serveur d’opation vidéo nouvellement ajouté dans le volet gauche du Générateur de topologie, cliquez dessus avec le bouton droit et choisissez **Modifier les propriétés.** Activez ou mettez à jour le port TCP ou TLS selon vos besoins et choisissez **OK.** Bien que le protocole TLS soit ajouté par défaut, seul TCP a été entièrement testé avec Cisco Unified Communications Manager (CallManager ou CUCM).
    
6. Ajoutez une passerelle vidéo. Pour ce faire, développez les composants partagés, cliquez avec le bouton droit sur **Passerelles vidéo** et sélectionnez **Nouvelle passerelle vidéo.**
    
7. Fournissez le FQDN ou l’adresse IP de la passerelle vidéo. La passerelle vidéo peut se voir dans un sous-domaine ou dans un autre domaine. Le CUCM utilisé par les VTC de votre système sert de passerelle vidéo.
    
8. Sélectionnez IPv4 ou IPv6 selon le cas. Vous pouvez utiliser toutes les adresses IP configurées ou limiter l’utilisation du service aux adresses IP sélectionnées.
    
9. Sélectionnez le port d’écoute de la passerelle vidéo. Sélectionnez le protocole de transport (TCP ou TLS) et associez-le à un serveur d’opation vidéo qui est installé pour une trunk SIP vidéo. Le protocole de transport de la passerelle vidéo doit correspondre au protocole de transport configuré pour le VIS.
    
10. Une vidéo SIP correspondante est ajoutée une fois l’étape ci-dessus terminée. Cliquez avec le bouton droit sur la trunke vidéo SIP, puis sélectionnez la trunk qui vient d’être ajoutée. Le nom de la trunk sip vidéo, le serveur d’interopage vidéo associé, le protocole de transport SIP et le port peuvent tous être modifiés. 
    
    > [!NOTE]
    >  Un serveur d’interconnexion vidéo prend en charge les trunks 1:N. Par conséquent, plusieurs branches peuvent être ajoutées, qui sont associées à un seul serveur d’interopivité vidéo, où chaque trunk s’termine sur une passerelle vidéo différente. La limitation est qu’une passerelle vidéo particulière dispose d’une seule et même Skype Entreprise Server déploiement.
  
11. Publiez le document de topologie comme décrit dans Créer et publier une nouvelle [topologie dans Skype Entreprise Server 2015](../../deploy/install/create-and-publish-new-topology.md).
    
    > [!NOTE]
    > Pour améliorer la résilience, vous souhaitez peut-être configurer un deuxième serveur d’interconnexion vidéo ou pool VIS, ou un pool frontal de sauvegarde. Pour plus [d’informations, voir mécanismes](../../plan-your-deployment/video-interop-server.md#resiliency) de résilience.
  
Toutes les tâches effectuées à l’aide du Générateur de topologie doivent maintenant être terminées. Procédez à l’installation du logiciel sur le ou les nouveaux serveurs VIS.
## <a name="see-also"></a>Voir aussi

[Déployer le rôle serveur VIS dans Skype Entreprise Server](deploy-the-vis-server-role.md)

[Planifier le serveur d’interconnexion vidéo dans Skype Entreprise Server](../../plan-your-deployment/video-interop-server.md)
  
[Créer et publier une topologie dans Skype Entreprise Server 2015](../../deploy/install/create-and-publish-new-topology.md)
