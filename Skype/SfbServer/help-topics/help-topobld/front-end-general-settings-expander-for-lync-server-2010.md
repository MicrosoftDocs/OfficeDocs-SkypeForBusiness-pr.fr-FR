---
title: Développeur des paramètres généraux du serveur frontal pour Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Vous modifiez les propriétés du pool frontal ou serveur frontal en modification ou en configurant les attributs suivants. La page de configuration est divisée en les sections suivantes :'
ms.openlocfilehash: 34f026b6e802bb83c550d2a81e5630a64765e27d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32180374"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Développeur des paramètres généraux du serveur frontal pour Lync Server 2010

Vous modifiez les propriétés du pool frontal ou serveur frontal en modification ou en configurant les attributs suivants. La page de configuration est divisée en les sections suivantes :

 **Général**

- **Nom de domaine complet**: le nom de domaine complet du pool frontal ou serveur frontal.

- Sélectionnez **utiliser toutes les adresses IP configurées** pour utiliser toutes les adresses configurées sur le pool frontal ou serveur frontal.

    > [!IMPORTANT]
    > Vous ne devez pas Sélectionnez cette option si vous colocalisez le serveur de médiation sur le serveur frontal ou un pool frontal. Serveurs de médiation et serveurs frontaux ont besoin des adresses IP dédiées de communication.

- Sélectionnez **limiter l’utilisation de service pour les adresses IP sélectionnées** et entrez l’adresse IP pour **l’adresse IP principale** pour la communication de pool frontal ou serveur frontal avec le reste du déploiement. Dans **adresse IP PSTN** , tapez l’adresse IP qui est associé avec le serveur de médiation.

    **Fonctions et fonctionnalités**

- **Conférence**: activez la case à cocher si vous souhaitez que les fonctionnalités de conférence dans votre déploiement. Conférence comprend l’audio, vidéo, partage d’application, le partage du bureau et les conférences Web. Vous devrez créer et associer un serveur Office Web Apps Server pour les conférences Web (définie plus loin dans cette page de propriétés).

- Si vous avez sélectionné la conférence, **conférence rendez-vous (PSTN)** peuvent être sélectionnés. Activez la case à cocher pour activer les fonctionnalités de conférence rendez-vous.

- Activez la case à cocher **Enterprise Voice** si vous envisagez de déployer des fonctionnalités à activer Lync Server 2013 pour agir comme système téléphonique vocale utilisant la téléphonie sur les technologies IP (VoIP), y compris la possibilité de déployer les téléphones combiné, SIP jonctions ou public connectivité du réseau téléphonique commuté à l’aide d’un serveur de médiation et IP-PBX, passerelles PSTN conjointement ou seul, basé sur la conception et la configuration requise. Pour des détails sur Enterprise Voice, consultez la rubrique [Enterprise Voice](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) et [Enterprise Voice dans Skype pour Business Server 2015 planifier](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Associations**

- **Magasin SQL Server**: nom de domaine complet du serveur SQL (et éventuellement une instance nommée) associé au pool frontal ou serveur frontal. Vous sélectionnez le magasin SQL Server dans la liste ou que vous créez un nouveau magasin SQL Server en cliquant sur **Nouveau**

- **Stocker des fichiers**: vous sélectionnez le nom de domaine complet du serveur et du partage (au format `\\<FQDN of server>\<share name>`) qui jouera le magasin de fichiers pour les fichiers partagés que Lync Server 2013 crée et utilise pour la réplication, les annuaires des conférences et autres fins. Vous sélectionnez le magasin de fichiers dans la liste ou si vous créez un nouveau magasin de fichiers en cliquant sur **Nouveau**.

- Activez la case à cocher **Associer un serveur d’archivage** pour activer un serveur d’archivage pour ce pool frontal ou serveur frontal. Après avoir sélectionné la case à cocher, vous sélectionnez un serveur d’archivage existante dans la liste ou cliquez sur **Nouveau** pour créer les définitions d’un nouveau serveur d’archivage.

- Activez la case à cocher **Associer un serveur de surveillance** pour activer un serveur de surveillance pour ce pool frontal ou serveur frontal. Après avoir sélectionné la case à cocher, vous sélectionnez un serveur de surveillance existant dans la liste ou cliquez sur **Nouveau** pour créer les définitions pour un nouveau serveur de surveillance.

- Sélectionnez le **associer un Pool de serveurs Edge (pour les composants multimédias** la case à cocher pour activer un serveur de périphérie pour ce pool frontal ou serveur frontal. Après avoir sélectionné la case à cocher, vous sélectionnez un serveur de transport Edge existant ou un pool dans la liste ou cliquez sur **Nouveau** pour créer les définitions pour un serveur Edge ou un pool.

  **Résilience**

- Sélectionnez la case à cocher de **pool de serveurs d’inscriptions de sauvegarde associé** à sélectionner dans la liste d’un pool frontal ou serveur frontal qui sera le serveur d’inscriptions de sauvegarde (autrement dit, le pool frontal ou serveur frontal désigné comme un serveur d’inscriptions secondaire dans le cas où le serveur principal Échec)

- Si vous sélectionné du pool de serveurs d’inscriptions de sauvegarde associé et que vous avez choisi un serveur d’inscriptions de sauvegarde, vous pouvez sélectionner la case à cocher pour **le basculement automatique et la restauration automatique pour la voix**. Vous pouvez maintenant définir des propriétés numériques pour **Voice basculement détection interne (s)** et un **intervalle de la restauration automatique voix (s)**. Pour plus d’informations, voir [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Services Web**

- Pour configurer les **services web internes**, vous définissez les **ports d’écoute** pour **HTTP** et **HTTPS**. Par défaut, voici le port TCP 80 et le port TCP 443, respectivement. Vous configurez également les **ports publiés** pour **HTTP** et **HTTPS**. Par défaut, voici le port TCP 80 et le port TCP 443, respectivement. Selon votre configuration des services web internes et utiliser des équilibreurs de charge (équilibreurs de charge matérielle et l’équilibrage de charge DNS), ajustez les valeurs de port pour définir l’écoute et les ports publiés.

    > [!IMPORTANT]
    > Services web internes et l’écoute défini et les ports publiés sont pour les clients internes et les appareils. Périphériques clients externes utilisent les services web externes à l’écoute et publiées ports, ainsi que le nom de domaine complet de services web externes définie (FQDN).

- Pour configurer **des services web externes**, vous définissez les **ports d’écoute** pour **HTTP** et **HTTPS**. Par défaut, voici le port TCP 80 et le port TCP 443, respectivement. Vous configurez également les **ports publiés** pour **HTTP** et **HTTPS**. Par défaut, voici le port TCP 80 et le port TCP 443, respectivement. Selon votre configuration des services web internes et utiliser des équilibreurs de charge (équilibreurs de charge matérielle et l’équilibrage de charge DNS), ajustez les valeurs de port pour définir l’écoute et les ports publiés.

    > [!IMPORTANT]
    > Services web externes et écoute défini les ports publiés sont pour les clients externes et les appareils. Périphériques clients externes utilisent les services web externes à l’écoute et publiées ports, généralement définies par le proxy inverse, ainsi que le nom de domaine complet de services web externes définie (FQDN). La relation entre les nom de domaine complet des services web externes et les URL simples définissent les adresses Web (URL) uniform resource identifier que les clients externes utilisera pour accéder aux services disponibles pour les utilisateurs externes et des périphériques. Pour plus d’informations sur les URL simples, voir [planification des URL simples](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).

  **Serveur de médiation**

- Pour configurer les propriétés du **Serveur de médiation** pour un serveur de médiation colocalisé (c'est-à-dire, un serveur de médiation déployés sur le pool frontal ou serveur frontal), sélectionnez le **serveur de médiation colocalisés**.

- Pour définir les **ports d’écoute** pour un serveur de médiation colocalisés, vous tapez la valeur du port **TLS** et **TCP** qui est à l’écoute sur le serveur de médiation colocalisés. Par défaut, TLS est défini en tant que le port TCP 5067.

- Pour définir une valeur de port TCP pour le serveur de médiation, vous activez la case à cocher **le port TCP activer** . Par défaut, le serveur de médiation utilise le transport layer security (TLS) sur le protocole TCP. Les ports TCP sont disponibles uniquement lorsque la sélection d’activer le Port TCP est activée.

    > [!NOTE]
    > Il s’agit d’un paramètre facultatif, et vous devez faire référence à la configuration requise de votre passerelle ou le PSTN afin de déterminer si vous devez ce. Par défaut, le port TCP est le port 5068.

- Vous définissez des jonctions associés avec le serveur de médiation colocalisés. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation.

    Si vous disposez de plusieurs passerelles associé à un serveur de médiation, vous pouvez spécifier la passerelle par défaut, sélectionnez la passerelle que vous souhaitez rendre la valeur par défaut, cliquez sur **Par défaut**. Si vous choisissez de supprimer la passerelle par défaut actuel, sélectionnez la passerelle, cliquez sur **Unmake la valeur par défaut**.

> [!IMPORTANT]
> Si vous apportez des modifications apportées aux propriétés dans cette boîte de dialogue, vous devez publier la topologie et exécutez le Skype pour l’Assistant de déploiement Business Server sur tous les serveurs concernés. Après avoir publié la nouvelle topologie, une liste des serveurs concernés où le Skype pour l’Assistant de déploiement Business Server doit être exécuté est fournie sous forme de lien dans l’écran Résumé publication réussie de topologie. Pour plus d’informations sur la publication de la topologie mise à jour, voir [publier la topologie](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Pour plus d’informations sur la Skype pour l’Assistant de déploiement Business Server, consultez la rubrique [Outils d’administration de Lync Server](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx).

Cliquez sur **OK** pour enregistrer et valider les modifications apportées au document de topologie.

Cliquez sur **Annuler** pour ignorer vos modifications et fermer **Modifier les propriétés** pour le pool frontal ou serveur frontal.

Cliquez sur **aide** pour lire cette rubrique d’aide.

## <a name="see-also"></a>Voir aussi

[Définir et configurer un Pool frontal ou un serveur Standard Edition Server](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
