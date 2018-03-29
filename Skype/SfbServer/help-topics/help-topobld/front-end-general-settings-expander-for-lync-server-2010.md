---
title: Développement de paramètres avant fin général pour Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Vous modifiez les propriétés du pool de serveur frontal ou de Front-End en modifiant ou en configurant les attributs suivants. La page de configuration est divisée dans les sections suivantes :'
ms.openlocfilehash: 2e249f1bd7f0f42cdc23429d79afde86d3f175a3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Développement de paramètres avant fin général pour Lync Server 2010
 
Vous modifiez les propriétés du pool de serveur frontal ou de Front-End en modifiant ou en configurant les attributs suivants. La page de configuration est divisée dans les sections suivantes :
  
 **Général**
  
- **Nom de domaine complet**: le nom de domaine complet du pool Front-End ou de serveur frontal.
    
- Sélectionnez **utiliser toutes les adresses IP configurées** pour rendre l’utilisation de toutes les adresses configurées sur le pool de Front-End ou de serveur frontal.
    
    > [!IMPORTANT]
    > Ne sélectionnez pas cette option si vous colocaliser sur le serveur frontal ou d’un pool frontal, le serveur de médiation. Les serveurs frontaux et les serveurs de médiation besoin des adresses IP dédiées de communication. 
  
- Sélectionnez **limiter l’utilisation de service aux adresses IP sélectionnées** et entrez l’adresse IP pour **l’adresse IP principale** pour la communication de pool Front-End ou de serveur frontal avec le reste du déploiement. Dans **adresse IP de réseau RTPC** , tapez l’adresse IP qui est associé avec le serveur de médiation.
    
    **Fonctions et fonctionnalités**
    
- **Conférence**: activez la case à cocher si vous souhaitez que les fonctionnalités de téléconférence dans votre déploiement. Inclut des conférences audio, vidéo, partage d’applications, le partage du bureau et les conférences Web. Vous devez créer et associer un serveur d’applications Web Office pour les conférences Web (définie plus loin dans cette page de propriétés).
    
- Si vous avez sélectionné la conférence, **(RTPC) d’accès à la conférence** peut être sélectionné. Activez la case à cocher pour activer les fonctionnalités de conférence à distance.
    
- Activez la case à cocher **De Voix Entreprise** si vous prévoyez de déployer des fonctionnalités à activer Lync Server 2013 d’agir comme système téléphonique vocale utilisant la téléphonie sur les technologies IP (VoIP), y compris la possibilité de déployer les téléphones combiné, SIP troncs ou public connectivité du réseau téléphonique commuté à l’aide du serveur de médiation et IP-PBX, passerelles RTPC en combinaison ou tout seul, en fonction de la conception et la configuration requise. Pour informations sur Voix Entreprise, consultez [Voix Entreprise](http://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) et la [planification de Voix Entreprise dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)
    
    **Associations**
    
- **Stockage de SQL Server**: nom de domaine complet de la SQL Server (et éventuellement une instance nommée) associé avec le serveur frontal ou Front-End le pool. Vous sélectionnez la banque d’informations de SQL Server à partir de la liste ou de vous créez un nouveau magasin de SQL Server en cliquant sur **Nouveau**
    
- **Stocker des fichiers**: vous sélectionnez le nom de domaine complet du serveur et du partage (au format `\\<FQDN of server>\<share name>`) qui agit comme l’emplacement de stockage de fichier pour les fichiers partagés que Lync Server 2013 crée et utilise pour la réplication, les répertoires de conférence et autres fins. Vous sélectionnez le stockage de fichiers dans la liste ou que vous créez une nouvelle banque de fichier en cliquant sur **Nouveau**.
    
- Cochez la case **d’Associer un serveur d’archivage** à l’activation d’un serveur d’archivage pour ce pool de Front-End ou de serveur frontal. Après avoir sélectionné la case à cocher, vous sélectionnez un serveur d’archivage existante dans la liste ou cliquez sur **Nouveau** pour créer les définitions pour un nouveau serveur d’archivage.
    
- Cochez la case **Associer Monitoring Server** pour activer un serveur de surveillance pour ce pool de Front-End ou de serveur frontal. Après avoir sélectionné la case à cocher, vous sélectionnez un serveur de surveillance existant dans la liste ou cliquez sur **Nouveau** pour créer les définitions pour un nouveau serveur de surveillance.
    
- Sélectionnez le **associer un Pool de bord (pour les composants de support** case à cocher pour activer un serveur de transport Edge pour ce pool de Front-End ou de serveur frontal. Après avoir sélectionné la case à cocher, vous activez un serveur de transport Edge existant ou le pool à partir de la liste ou cliquez sur **Nouveau** pour créer les définitions pour un serveur de transport Edge ou un pool.
    
 **Résilience**
  
- Cochez la case **pool de Registre de sauvegarde associé** pour sélectionner dans la liste un pool Front-End ou de serveur frontal qui sera le Registre de sauvegarde (, le serveur frontal ou Front-End le pool désigné comme un registraire secondaire dans le cas où le serveur principal ne fonctionne pas)
    
- Si vous sélectionné pool de Registre de sauvegarde associé et que vous avez choisi un Registre de sauvegarde, vous pouvez sélectionner la case à cocher pour le **basculement automatique sur incident et retour arrière pour la voix**. Vous pouvez maintenant définir des propriétés numériques pour **voix basculement détection interne (s)** et un **intervalle de restauration automatique de voix (s)**. Pour plus d’informations, consultez [planification de résilience de Voix Entreprise](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
    
 **Services Web**
  
- Pour configurer des **services web internes**, vous définissez les **ports d’écoute** pour **HTTP** et **HTTPS**. Par défaut, il s’agit de port TCP 80 et le port TCP 443, respectivement. Vous permet également de configurer les **ports de publié** pour **HTTP** et **HTTPS**. Par défaut, il s’agit de port TCP 80 et le port TCP 443, respectivement. En fonction de la configuration de vos services web internes et utiliser des équilibreurs de charge (équilibreurs de charge matériels et l’équilibrage de la charge DNS), ajuster les valeurs de port pour définir l’écoute et les ports disponibles.
    
    > [!IMPORTANT]
    > Services web internes et défini à l’écoute et des ports publiés sont pour les périphériques et les clients internes. Les clients externes et périphériques utilisent les services web externes à l’écoute et publié des ports, ainsi que le nom de domaine complet de services web externes définie (FQDN). 
  
- Pour configurer **des services web externes**, vous définissez les **ports d’écoute** pour **HTTP** et **HTTPS**. Par défaut, il s’agit de port TCP 80 et le port TCP 443, respectivement. Vous permet également de configurer les **ports de publié** pour **HTTP** et **HTTPS**. Par défaut, il s’agit de port TCP 80 et le port TCP 443, respectivement. En fonction de la configuration de vos services web internes et utiliser des équilibreurs de charge (équilibreurs de charge matériels et l’équilibrage de la charge DNS), ajuster les valeurs de port pour définir l’écoute et les ports disponibles.
    
    > [!IMPORTANT]
    > Services web externes et écoute définis et des ports publiés sont des périphériques et des clients externes. Les clients externes et périphériques utilisent les services web externes à l’écoute et publié des ports, généralement définis par votre proxy inverse ainsi que le nom de domaine complet de services web externes définie (FQDN). La relation entre les nom de domaine complet des services web externes et les URL Simple définissent les adresses uniform resource locator (URL) utilisées par les clients externes à accéder aux services disponibles pour les utilisateurs externes et périphériques. Pour plus d’informations sur les URL Simple, consultez [planification d’URL Simple](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx). 
  
 **Serveur de médiation**
  
- Pour configurer les propriétés de **Serveur de médiation** pour un serveur de médiation (autrement dit, un serveur de médiation déployés sur le serveur frontal ou Front-End le pool) colocalisée, sélectionnez **serveur de médiation de colocalisés activé**.
    
- Pour définir les **ports d’écoute** pour un serveur de médiation colocalisée, vous tapez la valeur du port **TCP** et de **TLS** qui est à l’écoute sur le serveur de médiation concurrentes. Par défaut, TLS est défini en tant que le port TCP 5067.
    
- Pour définir une valeur de port TCP du serveur de médiation, vous activez la case à cocher **Activer le TCP port** . Par défaut, le serveur de médiation utilise le transport layer security (TLS) sur le protocole TCP. Les ports TCP sont disponibles uniquement lorsque la sélection d’activer le Port TCP est activée.
    
    > [!NOTE]
    > Il s’agit d’un paramètre facultatif, et vous devez faire référence aux exigences de votre passerelle ou d’un RTPC pour déterminer si vous devez ce. Par défaut, le port TCP est le port 5068. 
  
- Vous permet de définir les puits associées avec le serveur de médiation colocalisée. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation.
    
    Si vous avez plus d’une passerelle associée à un serveur de médiation, vous pouvez spécifier la passerelle par défaut en sélectionnant la passerelle que vous souhaitez utiliser par défaut, cliquez sur **Utiliser par défaut**. Si vous choisissez de supprimer la passerelle par défaut actuelle, sélectionnez la passerelle et cliquez sur **Unmake la valeur par défaut**.
    
> [!IMPORTANT]
> Si vous apportez des modifications aux propriétés dans cette boîte de dialogue, vous devez publier la topologie et exécuter le Skype pour l’Assistant de déploiement de Business Server sur tous les serveurs affectés. Après avoir publié la nouvelle topologie, une liste de serveurs concernés où le Skype pour l’Assistant de déploiement de Business Server doit être exécutée est fournie pour vous en tant que lien dans l’écran de résumé publication réussie de topologie. Pour plus d’informations sur la publication de la topologie de mise à jour, reportez-vous à la section [publier la topologie](http://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Pour plus d’informations sur le Skype pour l’Assistant de déploiement de Business Server, reportez-vous à la section [Outils d’administration de Lync Server](http://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx). 
  
Cliquez sur **OK** pour enregistrer et valider vos modifications dans le document de la topologie.
  
Cliquez sur **Annuler** pour ignorer vos modifications et fermer les **Modifier les propriétés** pour le pool de Front-End ou de serveur frontal.
  
Cliquez sur **aide** pour lire cette rubrique d’aide.
  
## <a name="see-also"></a>Voir aussi

#### 

[Définir et configurer un serveur Standard Edition Server ou un Pool frontal](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)

