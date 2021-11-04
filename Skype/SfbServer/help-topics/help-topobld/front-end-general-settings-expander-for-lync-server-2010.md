---
title: Expanseur des paramètres généraux du serveur frontal pour Lync Server 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Vous modifiez les propriétés du serveur frontal ou du pool frontal en éditant ou en configurant les attributs suivants. La page de configuration s’organise autour des sections suivantes :'
ms.openlocfilehash: d7257a8abf61f2d081562e72b40811017dcefaa0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768772"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Expandeur des paramètres généraux du serveur frontal pour Lync Server 2010

Vous modifiez les propriétés du serveur frontal ou du pool frontal en éditant ou en configurant les attributs suivants. La page de configuration s’organise autour des sections suivantes :

 **Général**

- **FQDN :** nom de domaine complet du serveur frontal ou du pool frontal.

- Sélectionnez **Utiliser toutes les adresses IP configurées** pour utiliser toutes les adresses configurées sur le serveur frontal ou le pool frontal.

    > [!IMPORTANT]
    > Vous ne devez pas sélectionner cette option si vous coloquez le serveur de médiation sur le serveur frontal ou le pool frontal. Les serveurs de médiation et les serveurs frontaux ont besoin d’adresses IP dédiées sur lesquelles communiquer.

- Sélectionnez Limiter l’utilisation du service aux **adresses IP sélectionnées** et entrez l’adresse IP de l’adresse **IP** principale pour la communication entre le serveur frontal ou le pool frontal avec le reste du déploiement. Tapez dans **l’adresse IP PSTN** l’adresse IP associée au serveur de médiation.

    **Fonctionnalités**

- **Conférence** : activez cette case à cocher si vous voulez mettre en œuvre des fonctionnalités de conférence dans votre déploiement. Ces dernières comprennent l’audio, la vidéo, le partage des applications, le partage du Bureau et la conférence web. Vous devez créer et associer un serveur web apps Office pour la conférence Web (défini plus loin dans cette page Propriétés).

- Si vous avez sélectionné Conférence, **Conférence rendez-vous (PSTN)** peut l’être également. Activez cette case à cocher pour mettre en œuvre les fonctionnalités de conférence rendez-vous.

- Activez la case à cocher **Voix Entreprise** si vous avez l’intention de déployer des fonctionnalités permettant à Lync Server 2013 d’agir en tant que système vocal téléphonique à l’aide des technologies VoIP (Voice over IP), notamment l’option de déploiement de téléphones combinés, de connexions SIP ou de connectivité réseau téléphonique commuté public à l’aide du serveur de médiation, des passerelles PSTN et du système IP-PBX, en combinaison ou seul,  en fonction de la conception et des exigences. Pour plus d’Voix Entreprise, voir [Voix Entreprise](/previous-versions/office/lync-server-2013/lync-server-2013-enterprise-voice) et Planifier Voix Entreprise dans [Skype Entreprise Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Associations**

- **SQL Server store**: le nom de SQL Server (et éventuellement une instance nommée) associé au serveur frontal ou au pool frontal. Vous sélectionnez le magasin SQL Server dans la liste ou vous créez un magasin SQL Server en cliquant sur **Nouveau**.

- Magasin de fichiers : vous sélectionnez le nom deqdn du serveur et le partage (au format ) qui sert d’emplacement de magasin de fichiers pour les fichiers partagés que `\\<FQDN of server>\<share name>` Lync Server 2013 crée et utilise à des fins de réplication, d’annuaires de conférences et d’autres fins. Vous sélectionnez le magasin de fichiers dans la liste ou vous créez un magasin de fichiers en cliquant sur **Nouveau**.

- Activez **la case à cocher** Associer un serveur d’archivage pour activer un serveur d’archivage pour ce serveur frontal ou pool frontal. Après avoir cocher la case, vous sélectionnez un serveur d’archivage existant dans la liste ou cliquez sur **Nouveau** pour créer les définitions d’un nouveau serveur d’archivage.

- Activez la **case à cocher Associer** un serveur de surveillance pour activer un serveur de surveillance pour ce serveur frontal ou pool frontal. Après avoir cocher la case, vous sélectionnez un serveur de surveillance existant dans la liste ou cliquez sur **Nouveau** pour créer les définitions d’un nouveau serveur de surveillance.

- Activez la case à cocher Associer un pool de serveurs Edge (pour les **composants multimédias)** pour activer un serveur Edge pour ce serveur frontal ou pool frontal. Après avoir cocher la case, vous sélectionnez un serveur Edge ou un pool de serveurs Edge existants dans la liste ou cliquez sur **Nouveau** pour créer les définitions d’un nouveau serveur Edge ou pool de serveurs Edge.

  **Résilience**

- Cochez la case Pool de serveurs d’inscriptions de sauvegarde associé pour sélectionner dans la liste un serveur frontal ou pool frontal qui sera le serveur d’inscriptions de sauvegarde (c’est-à-dire, le serveur frontal ou le pool frontal désigné comme serveur d’inscriptions secondaire en cas de panne du serveur principal) 

- Si vous avez sélectionné Pool de serveurs d’inscriptions de sauvegarde associé et si vous avez choisi un serveur d’inscriptions de sauvegarde, vous pouvez activer la case à cocher **Basculement et restauration automatiques pour Voice**. Vous pouvez maintenant définir des propriétés numériques pour **Intervalle de détection d’échec Voice (en secondes)** et **Intervalle de restauration automatique Voice (en secondes)**. Pour plus d’informations, voir [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)

  **Services web**

- Pour configurer **Services web internes**, vous définissez **Ports d’écoute** pour **HTTP** et **HTTPS**. Par défaut, il s’agit respectivement du port TCP 80 et du port TCP 443. Vous configurez également les **Ports publiés** pour **HTTP** et **HTTPS**. Par défaut, il s’agit respectivement du port TCP 80 et du port TCP 443. Selon votre configuration des services web internes et votre utilisation des équilibrages de charge (équilibrages de charge matérielle et DNS), réglez les valeurs des ports pour définir les ports d’écoute et publiés.

    > [!IMPORTANT]
    > Les services web internes et les ports d’écoute et publiés sont destinés aux clients et périphériques internes. Les clients et périphériques externes utilisent les ports d’écoute et publiés des services web externes, avec le nom de domaine complet (FQDN) des services web externes définis.

- Pour configurer **Services web externes**, vous définissez **Ports d’écoute** pour **HTTP** et **HTTPS**. Par défaut, il s’agit respectivement du port TCP 80 et du port TCP 443. Vous configurez également les **Ports publiés** pour **HTTP** et **HTTPS**. Par défaut, il s’agit respectivement du port TCP 80 et du port TCP 443. Selon votre configuration des services web internes et votre utilisation des équilibrages de charge (équilibrages de charge matérielle et DNS), réglez les valeurs des ports pour définir les ports d’écoute et publiés.

    > [!IMPORTANT]
    > Les services web externes et les ports d’écoute et publiés sont destinés aux clients et périphériques externes. Les clients et périphériques externes utilisent les ports d’écoute et publiés des services web externes, généralement définis par votre proxy inverse, avec le nom de domaine complet (FQDN) des services web externes définis. Les relations qui existent entre le nom de domaine complet (FQDN) des services web externes définis et les URL simples définissent les adresses URL (Uniform Resource Locator) que les clients externes utiliseront pour accéder aux services disponibles pour les utilisateurs et les périphériques externes. Pour plus d’informations sur les URL simples, voir [Planning for Simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls).

  **Serveur de médiation**

- Pour configurer  les propriétés du serveur de médiation pour un serveur de médiation cococéré (c’est-à-dire, un serveur de médiation déployé sur le serveur frontal ou le pool frontal), sélectionnez Serveur de médiation cococéré **activé.**

- Pour définir les **ports d’écoute** d’un serveur de médiation câpisé, tapez la valeur du port **TLS** et **TCP** sur qui le serveur de médiation câpisé écoute. Par défaut, TLS est défini comme le port TCP 5067.

- Pour définir une valeur de port TCP pour le serveur de médiation, activez la case à cocher Activer le **port TCP.** Par défaut, le serveur de médiation utilise le protocole TLS (Transport Layer Security) sur le protocole TCP. Les ports TCP sont disponibles uniquement lorsqu’est activée la sélection Activer le port TCP.

    > [!NOTE]
    > Il s’agit d’un paramètre facultatif et vous devriez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, la valeur du port TCP est 5068.

- Vous définissez des jonctions associées au serveur de médiation colocalisé. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation.

    Si plusieurs passerelles sont associées à un serveur de médiation, vous pouvez spécifier la passerelle par défaut en sélectionnant la passerelle que vous souhaitez utiliser par défaut, puis en cliquant sur Utiliser par **défaut.** Si vous choisissez de supprimer la passerelle par défaut actuelle, sélectionnez-la, puis cliquez sur **Annuler Par défaut**.

> [!IMPORTANT]
> Si vous modifiez les propriétés de cette boîte de dialogue, vous devez publier la topologie et exécuter l’Assistant Déploiement Skype Entreprise Server sur tous les serveurs concernés. Après la publication de la nouvelle topologie, une liste des serveurs affectés sur lequel l’Assistant déploiement Skype Entreprise Server doit être exécuté est fournie sous forme de lien sur l’écran récapitulatif de publication de la topologie. Pour plus d’informations sur la publication de la topologie mise à jour, voir [Publish the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-topology). Pour plus d’informations sur l Skype Entreprise Server de déploiement, voir [outils d’administration Lync Server.](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-administrative-tools)

Cliquez sur **OK** pour enregistrer et valider les modifications que vous avez apportées au document de topologie.

Cliquez **sur Annuler** pour ignorer vos modifications et fermer **les** propriétés de modification pour le serveur frontal ou le pool frontal.

Cliquez sur **Aide** pour lire cette rubrique d’aide.

## <a name="see-also"></a>Voir aussi

[Définition et configuration d’un pool frontal ou d’un serveur Standard Edition Server](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)