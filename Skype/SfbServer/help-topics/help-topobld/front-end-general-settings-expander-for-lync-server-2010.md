---
title: Expanseur des paramètres généraux du serveur frontal pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Pour modifier les propriétés du serveur frontal ou du pool frontal, modifiez ou configurez les attributs suivants. La page de configuration s’organise autour des sections suivantes :'
ms.openlocfilehash: 6d7cdb9067ff88b383077538e38c39c2f8e86a5a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219095"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Expanseur des paramètres généraux du serveur frontal pour Lync Server 2010

Pour modifier les propriétés du serveur frontal ou du pool frontal, modifiez ou configurez les attributs suivants. La page de configuration s’organise autour des sections suivantes :

 **Général**

- Nom de domaine **complet (FQDN)**: nom de domaine complet du serveur frontal ou du pool frontal.

- Sélectionnez **utiliser toutes les adresses IP configurées** pour utiliser toutes les adresses configurées sur le serveur frontal ou le pool frontal.

    > [!IMPORTANT]
    > Vous ne devez pas sélectionner cette option si vous colocaliser le serveur de médiation sur le serveur frontal ou le pool frontal. Les serveurs de médiation et les serveurs frontaux ont besoin d’adresses IP dédiées sur lesquelles communiquer.

- Sélectionnez **limiter l’utilisation des services aux adresses IP sélectionnées** et entrez l’adresse IP de l' **adresse IP principale** pour le serveur frontal ou la communication de pool frontal avec le reste du déploiement. Tapez dans **adresse IP RTC** l’adresse IP associée au serveur de médiation.

    **Fonctionnalités**

- **Conférence** : activez cette case à cocher si vous voulez mettre en œuvre des fonctionnalités de conférence dans votre déploiement. Ces dernières comprennent l’audio, la vidéo, le partage des applications, le partage du Bureau et la conférence web. Vous devrez créer et associer un serveur Office Web Apps Server pour la conférence Web (défini plus loin dans cette page de propriétés).

- Si vous avez sélectionné Conférence, **Conférence rendez-vous (PSTN)** peut l’être également. Activez cette case à cocher pour mettre en œuvre les fonctionnalités de conférence rendez-vous.

- Activez la case à cocher **voix entreprise** si vous envisagez de déployer des fonctionnalités pour permettre à Lync Server 2013 de se comporter comme votre système vocal de téléphonie à l’aide des technologies VoIP (Voice over IP). y compris la possibilité de déployer des téléphones combinés, des jonctions SIP ou une connectivité de réseau téléphonique commuté public à l’aide du serveur de médiation, de passerelles PSTN et d’IP-PBX, en combinaison ou uniquement, en fonction de la conception et des exigences. Pour plus d’informations sur voix entreprise, voir [voix entreprise](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) et [plan pour voix entreprise dans Skype entreprise Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Associations**

- **Magasin SQL Server**: nom de domaine complet (FQDN) du serveur SQL Server (et éventuellement une instance nommée) associé au serveur frontal ou au pool frontal. Vous sélectionnez le magasin SQL Server dans la liste ou vous créez un magasin SQL Server en cliquant sur **Nouveau**.

- **Magasin de fichiers**: sélectionnez le nom de domaine complet (FQDN) du serveur et le partage (au format  `\\<FQDN of server>\<share name>` ) qui servira d’emplacement du magasin de fichiers pour les fichiers partagés créés et utilisés par Lync Server 2013 pour la réplication, les annuaires de conférence et d’autres objectifs. Vous sélectionnez le magasin de fichiers dans la liste ou vous créez un magasin de fichiers en cliquant sur **Nouveau**.

- Activez la case à cocher **associer un serveur d’archivage** pour activer un serveur d’archivage pour ce serveur frontal ou ce pool frontal. Après avoir activé la case à cocher, sélectionnez un serveur d’archivage existant dans la liste ou cliquez sur **nouveau** pour créer les définitions d’un nouveau serveur d’archivage.

- Activez la case à cocher **associer un serveur de surveillance** pour activer un serveur de surveillance pour ce serveur frontal ou ce pool frontal. Après avoir activé la case à cocher, sélectionnez un serveur de surveillance existant dans la liste ou cliquez sur **nouveau** pour créer les définitions d’un nouveau serveur de surveillance.

- Activez la case à cocher **associer un pool Edge (pour les composants multimédias** ) pour activer un serveur Edge pour ce serveur frontal ou ce pool frontal. Après avoir activé la case à cocher, sélectionnez un serveur Edge ou un pool existant dans la liste ou cliquez sur **nouveau** pour créer les définitions d’un nouveau serveur ou pool Edge.

  **Résilience**

- Activez la case à cocher pool de serveurs d' **inscriptions de sauvegarde associé** pour sélectionner dans la liste un serveur frontal ou un pool frontal qui sera le serveur d’inscriptions de sauvegarde (c’est-à-dire, le serveur frontal ou le pool frontal désigné comme serveur d’inscriptions secondaire en cas de panne du serveur principal).

- Si vous avez sélectionné Pool de serveurs d’inscriptions de sauvegarde associé et si vous avez choisi un serveur d’inscriptions de sauvegarde, vous pouvez activer la case à cocher **Basculement et restauration automatiques pour Voice**. Vous pouvez maintenant définir des propriétés numériques pour **Intervalle de détection d’échec Voice (en secondes)** et **Intervalle de restauration automatique Voice (en secondes)**. Pour plus d’informations, voir [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Services web**

- Pour configurer **Services web internes**, vous définissez **Ports d’écoute** pour **HTTP** et **HTTPS**. Par défaut, il s’agit respectivement du port TCP 80 et du port TCP 443. Vous configurez également les **Ports publiés** pour **HTTP** et **HTTPS**. Par défaut, il s’agit respectivement du port TCP 80 et du port TCP 443. Selon votre configuration des services web internes et votre utilisation des équilibrages de charge (équilibrages de charge matérielle et DNS), réglez les valeurs des ports pour définir les ports d’écoute et publiés.

    > [!IMPORTANT]
    > Les services web internes et les ports d’écoute et publiés sont destinés aux clients et périphériques internes. Les clients et périphériques externes utilisent les ports d’écoute et publiés des services web externes, avec le nom de domaine complet (FQDN) des services web externes définis.

- Pour configurer **Services web externes**, vous définissez **Ports d’écoute** pour **HTTP** et **HTTPS**. Par défaut, il s’agit respectivement du port TCP 80 et du port TCP 443. Vous configurez également les **Ports publiés** pour **HTTP** et **HTTPS**. Par défaut, il s’agit respectivement du port TCP 80 et du port TCP 443. Selon votre configuration des services web internes et votre utilisation des équilibrages de charge (équilibrages de charge matérielle et DNS), réglez les valeurs des ports pour définir les ports d’écoute et publiés.

    > [!IMPORTANT]
    > Les services web externes et les ports d’écoute et publiés sont destinés aux clients et périphériques externes. Les clients et périphériques externes utilisent les ports d’écoute et publiés des services web externes, généralement définis par votre proxy inverse, avec le nom de domaine complet (FQDN) des services web externes définis. Les relations qui existent entre le nom de domaine complet (FQDN) des services web externes définis et les URL simples définissent les adresses URL (Uniform Resource Locator) que les clients externes utiliseront pour accéder aux services disponibles pour les utilisateurs et les périphériques externes. Pour plus d’informations sur les URL simples, voir [Planning for Simple URLs](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).

  **Serveur de médiation**

- Pour configurer les propriétés du **serveur de médiation** pour un serveur de médiation colocalisé (c’est-à-dire un serveur de médiation déployé sur le serveur frontal ou le pool frontal), sélectionnez **serveur de médiation colocalisé activé**.

- Pour définir les **ports d’écoute** d’un serveur de médiation colocalisé, tapez la valeur du port **TLS** et du port **TCP** sur lequel le serveur de médiation colocalisé est à l’écoute. Par défaut, TLS est défini comme le port TCP 5067.

- Pour définir une valeur de port TCP pour le serveur de médiation, activez la case à cocher **activer le port TCP** . Par défaut, le serveur de médiation utilise le protocole TLS (Transport Layer Security) sur TCP. Les ports TCP sont disponibles uniquement lorsqu’est activée la sélection Activer le port TCP.

    > [!NOTE]
    > Il s’agit d’un paramètre facultatif et vous devriez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, la valeur du port TCP est 5068.

- Vous définissez des jonctions associées au serveur de médiation colocalisé. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation.

    Si plusieurs passerelles sont associées à un serveur de médiation, vous pouvez spécifier la passerelle par défaut en sélectionnant la passerelle à utiliser par défaut, puis en cliquant sur **utiliser par défaut**. Si vous choisissez de supprimer la passerelle par défaut actuelle, sélectionnez-la, puis cliquez sur **Annuler Par défaut**.

> [!IMPORTANT]
> Si vous modifiez les propriétés de cette boîte de dialogue, vous devez publier la topologie et exécuter l’Assistant Déploiement de Skype entreprise Server sur tous les serveurs concernés. Une fois la nouvelle topologie publiée, la liste des serveurs concernés sur lesquels l’Assistant Déploiement de Skype entreprise Server doit être exécuté vous est fournie sous forme de lien sur l’écran Résumé de publication de la topologie réussie. Pour plus d’informations sur la publication de la topologie mise à jour, voir [Publish the Topology](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Pour plus d’informations sur l’Assistant Déploiement de Skype entreprise Server, reportez-vous à la rubrique [Outils d’administration de Lync Server](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx).

Cliquez sur **OK** pour enregistrer et valider les modifications que vous avez apportées au document de topologie.

Cliquez sur **Annuler** pour ignorer vos modifications et fermer les **Propriétés de modification** pour le serveur frontal ou le pool frontal.

Cliquez sur **Aide** pour lire cette rubrique d’aide.

## <a name="see-also"></a>Voir aussi

[Définition et configuration d’un pool frontal ou d’un serveur Standard Edition Server](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
