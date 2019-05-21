---
title: Développeur des paramètres généraux du serveur frontal pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Vous pouvez modifier les propriétés du serveur frontal ou du pool de front-end en modifiant ou en configurant les attributs suivants. La page Configuration est divisée en sections suivantes:'
ms.openlocfilehash: b0ee8a2d0081d937bf93d4a638e4f56b1cc79134
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284402"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Développeur des paramètres généraux du serveur frontal pour Lync Server 2010

Vous pouvez modifier les propriétés du serveur frontal ou du pool de front-end en modifiant ou en configurant les attributs suivants. La page Configuration est divisée en sections suivantes:

 **Général**

- **FQDN**: nom de domaine complet du serveur frontal ou du pool frontal.

- Sélectionnez **utiliser toutes les adresses IP configurées** pour utiliser toutes les adresses configurées sur le serveur frontal ou le pool frontal.

    > [!IMPORTANT]
    > Vous ne devez pas sélectionner cette option si vous collocate le serveur de médiation sur le serveur frontal ou le pool frontal. Les serveurs de médiation et les serveurs frontaux doivent disposer d’adresses IP dédiées sur lesquelles communiquer.

- Sélectionnez **limiter l’utilisation du service aux adresses IP sélectionnées** et entrez l’adresse IP de l' **adresse IP principale** du serveur frontal ou du pool frontal pour communiquer avec le reste du déploiement. Tapez **adresse IP RTC** et adresse IP associée au serveur de médiation.

    **Fonctionnalités et fonctionnalités**

- **Conférences**: activez la case à cocher si vous voulez utiliser les fonctionnalités de conférence dans votre déploiement. Les conférences incluent l’audio, la vidéo, le partage d’application, le partage de bureau et la conférence Web. Vous devez créer et associer une application Office Web Apps Server pour les conférences Web (définie plus loin dans cette page de propriétés).

- Si vous avez sélectionné une conférence rendez **-vous (RTC)** , vous pouvez sélectionner l’option Conférence rendez-vous. Activez les cases à cocher pour activer les fonctionnalités de conférence rendez-vous.

- Activez la case à cocher **entreprise voix** si vous envisagez de déployer des fonctionnalités permettant à Lync Server 2013 de fonctionner comme votre système vocal par téléphone à l’aide de technologies de voix sur IP (VoIP), y compris la possibilité de déployer des téléphones portables, des lignes SIP ou du public connexion réseau téléphonique commutée à l’aide d’un serveur de médiation, de passerelles RTC et de PBX IP, en combinaison ou seule, en fonction de la conception et des exigences. Pour plus d’informations sur voix entreprise, reportez-vous à la section voix [entreprise](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) et [plan pour Enterprise Voice dans Skype entreprise Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Associations**

- **SQL Server Store**: nom de domaine complet du serveur SQL (et éventuellement d’une instance nommée) associé au serveur frontal ou au pool frontal. Vous sélectionnez le magasin SQL Server dans la liste ou vous créez une nouvelle banque SQL Server en cliquant sur **nouveau**

- **Magasin de fichiers**: vous sélectionnez le nom de domaine complet (FQDN) du serveur et `\\<FQDN of server>\<share name>`le partage (au format) qui servira d’emplacement de stockage de fichiers pour les fichiers partagés que Lync Server 2013 crée et utilise pour la réplication, les annuaires de conférences et autres objectifs. Pour sélectionner le magasin de fichiers dans la liste, vous devez créer un nouveau magasin de fichiers en cliquant sur **nouveau**.

- Cochez la case **associer un serveur** d’archivage pour activer un serveur d’archivage pour ce serveur frontal ou une liste frontale. Après avoir coché la case, sélectionnez un serveur d’archivage existant dans la liste ou cliquez sur **nouveau** pour créer les définitions d’un nouveau serveur d’archivage.

- Activez la case à cocher **associer le serveur de surveillance** pour activer un serveur de surveillance pour ce serveur frontal ou le pool frontal. Après avoir coché la case, sélectionnez un serveur de surveillance existant dans la liste ou cliquez sur **nouveau** pour créer les définitions d’un nouveau serveur de surveillance.

- Activez la case à cocher **associer le pool Edge (pour les composants multimédias** ) pour activer un serveur Edge pour ce serveur frontal ou le pool frontal. Après avoir activé la case à cocher, vous sélectionnez un serveur Edge ou un pool existant dans la liste ou cliquez sur **nouveau** pour créer les définitions d’un nouveau serveur Edge ou pool.

  **Résilience**

- Activez la case à cocher **pool d’registraire de sauvegarde associé** pour sélectionner dans la liste un serveur frontal ou une liste frontale qui sera le Bureau d’enregistrement de sauvegarde (c’est-à-dire, le serveur frontal ou le pool frontal désigné comme bureau d’enregistrement secondaire dans le cas où le principal défaillant

- Si vous avez sélectionné le pool d’inscriptions de sauvegarde associé et que vous avez choisi un bureau d’enregistrement de sauvegarde, vous pouvez activer la case à cocher **reprise automatique et retour automatique pour la voix**. À présent, vous pouvez définir des propriétés numériques pour la détection de la **reprise vocale** et l' **intervalle de restauration vocale (s)**. Pour plus d’informations, consultez [planification de la résilience vocale d’entreprise](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx) .

  **Services Web**

- Pour configurer les **services Web internes**, vous définissez des **ports d’écoute** pour **http** et **https**. Par défaut, il s’agit de port TCP 80 et 443 de port TCP respectivement. Vous devez également configurer les **ports publiés** pour **http** et **https**. Par défaut, il s’agit de port TCP 80 et 443 de port TCP respectivement. En fonction de la configuration de vos services Web internes et de l’utilisation des équilibreurs de charge (équilibreurs de charge matérielle et équilibrage de la charge DNS), ajustez les valeurs de port pour définir les ports d’écoute et de publication.

    > [!IMPORTANT]
    > Les services Web internes ainsi que les ports d’écoute et de publication définis sont destinés aux clients et appareils internes. Les clients et périphériques externes utilisent les ports d’écoute et de publication des services Web externes, ainsi que le nom de domaine complet des services Web externes définis.

- Pour configurer des **services Web externes**, vous définissez des **ports d’écoute** pour **http** et **https**. Par défaut, il s’agit de port TCP 80 et 443 de port TCP respectivement. Vous devez également configurer les **ports publiés** pour **http** et **https**. Par défaut, il s’agit de port TCP 80 et 443 de port TCP respectivement. En fonction de la configuration de vos services Web internes et de l’utilisation des équilibreurs de charge (équilibreurs de charge matérielle et équilibrage de la charge DNS), ajustez les valeurs de port pour définir les ports d’écoute et de publication.

    > [!IMPORTANT]
    > Les services Web externes ainsi que les ports d’écoute et publiés définis sont destinés aux clients et périphériques externes. Les clients et périphériques externes utilisent les ports d’écoute et de publication des services Web externes, généralement définis par votre proxy inverse, ainsi que le nom de domaine complet (FQDN) des services Web externes définis. La relation du nom de domaine complet des services Web externes et des URL simples définissent les adresses URL (Uniform Resource Locator) que les clients externes utiliseront pour accéder aux services accessibles aux utilisateurs et périphériques externes. Pour plus d’informations sur les URL simples, voir [planification d’URL simples](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).

  **Serveur de médiation**

- Pour configurer les propriétés du **serveur** de médiation pour un serveur de médiation colocalisé (autrement dit, un serveur de médiation déployé sur le serveur frontal ou le pool frontal), sélectionnez **serveur de médiation en option activé**.

- Pour définir les **ports d’écoute** d’un serveur de médiation colocalisé, vous devez taper les valeurs de port **TLS** et **TCP** que le serveur de médiation coordonnés écoute. Par défaut, la valeur TLS est définie comme port TCP 5067.

- Pour définir une valeur de port TCP pour le serveur de médiation, activez la case à cocher **activer le port TCP** . Par défaut, le serveur de médiation utilise le protocole TLS (Transport Layer Security) sur TCP. Les ports TCP ne sont disponibles que lorsque l’option Activer le port TCP est activée.

    > [!NOTE]
    > Il s’agit d’un paramètre facultatif qui vous permet de consulter les exigences de votre passerelle ou de votre PSTN pour déterminer si vous en avez besoin. Par défaut, le port TCP est le port 5068.

- Vous définissez les lignes associées au serveur de médiation colocalisé. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation.

    Si vous avez plusieurs passerelles associées à un serveur de médiation, vous pouvez spécifier la passerelle par défaut en sélectionnant la passerelle que vous voulez utiliser par défaut, puis en cliquant sur **définir par défaut**. Si vous choisissez de supprimer la passerelle par défaut actuelle, sélectionnez celle-ci, puis cliquez sur **créer la valeur par défaut**.

> [!IMPORTANT]
> Si vous apportez des modifications aux propriétés de cette boîte de dialogue, vous devez publier la topologie et exécuter l’Assistant Déploiement de Skype entreprise Server sur tous les serveurs concernés. Après la publication de la nouvelle topologie, une liste des serveurs concernés dans lesquels l’Assistant Déploiement de Skype entreprise Server doit s’exécuter est disponible en tant que lien sur l’écran de synthèse de publication de la topologie réussie. Pour plus d’informations sur la publication de la topologie mise à jour, voir [publier la topologie](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Pour plus d’informations sur l’Assistant Déploiement de Skype entreprise Server, voir [Outils d’administration de Lync Server](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx).

Cliquez sur **OK** pour enregistrer et valider les modifications apportées au document topologique.

Cliquez sur **Annuler** pour ignorer vos modifications et fermer les **Propriétés de modification** du serveur frontal ou du pool frontal.

Cliquez sur **aide** pour lire cette rubrique d’aide.

## <a name="see-also"></a>Voir aussi

[Définir et configurer un pool frontal ou un serveur Standard Edition Server](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
