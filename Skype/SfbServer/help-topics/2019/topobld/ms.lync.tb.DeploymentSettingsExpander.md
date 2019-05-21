---
title: Expanseur des paramètres de déploiement
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DeploymentSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7220ec1f-38cb-4297-870e-591a832cd2f2
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous pouvez modifier les propriétés d’un déploiement existant à l’aide des sections suivantes :'
ms.openlocfilehash: 84e4873b098c6d3cf650c71653456b22179fa44c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280562"
---
# <a name="deployment-settings-expander"></a>Expanseur des paramètres de déploiement

Vous pouvez modifier les propriétés d’un déploiement existant à l’aide des sections suivantes :

- Domaine SIP

- URL simples 

- serveur de gestion centralisée

## <a name="sip-domain"></a>Domaine SIP

Pour modifier le **Domaine SIP par défaut**, entrez le nouveau nom de domaine.

Pour ajouter d’**autres domaines SIP pris en charge**, tapez le nom de domaine à ajouter. Cliquez sur **Ajouter** pour le valider comme nouveau nom de domaine SIP (Session Initiation Protocol).

Pour mettre à jour un nom de domaine SIP existant, sélectionnez le nom de domaine et effectuez les modifications dans la zone de texte. Cliquez sur **Mettre à jour** pour valider la modification.

Pour supprimer un autre nom de domaine SIP défini, sélectionnez le nom de domaine, puis cliquez sur **Supprimer**.

Lorsque vous avez terminé vos modifications dans la page Modifier les propriétés, cliquez sur **OK** pour les enregistrer. Cliquez sur **Annuler** pour annuler les modifications.

## <a name="simple-urls"></a>URL simples

Pour modifier ou définir des URL simples, vous devez sélectionner l’une des trois URL simples à modifier. Vous pouvez sélectionner les URL d’accès téléphonique, les URL de réunion ou les URL d’accès administratif.

Pour modifier l’URL d’accès téléphonique ou l’URL de réunion, sélectionnez l’URL à modifier. Cliquez sur **Modifier l’URL**. Ensuite, modifiez l’URL, puis cliquez sur **OK** pour l’enregistrer. Cliquez sur **Annuler** pour annuler les modifications.

Pour ajouter une nouvelle URL, cliquez sur **Ajouter**. Dans la boîte de dialogue **Ajouter une URL simple**, spécifiez l’URL et cliquez sur **OK** pour l’enregistrer. Sélectionnez **Définir cette URL en tant qu’URL active pour le domaine sélectionné** si vous avez besoin de définir la nouvelle URL comme URL active. Cliquez sur **Annuler** pour annuler les modifications.

Pour définir une autre URL comme URL active (identifiée par une coche verte en regard de l’URL), sélectionnez l’URL, puis cliquez sur **Rendre actif**.

> [!NOTE]
> Il ne peut y avoir qu’une seule URL active pour chaque domaine SIP.

Si vous devez supprimer une URL, sélectionnez-la et cliquez sur **Supprimer**.

> [!CAUTION]
> Lisez attentivement les informations dans la page de boîte de dialogue des paramètres des URL simples. La suppression de l’URL d’une réunion provoque l’indisponibilité des réunions déjà planifiées par les utilisateurs. Pensez à laisser l’URL précédente après l’activation de la nouvelle URL de réunion. Vous pouvez supprimer l’ancienne URL de réunion lorsque vous êtes sûr que les utilisateurs ne s’en servent plus.

Pour modifier l’URL d’accès administratif, modifiez l’entrée.

Lorsque vous avez terminé vos modifications dans la page Modifier les propriétés, cliquez sur **OK** pour les enregistrer. Cliquez sur **Annuler** pour annuler les modifications.

## <a name="central-management-server"></a>Serveur de gestion centralisée

Le serveur de gestion centralisée peut être changé d’un pool frontal défini à un autre. Pour modifier l’emplacement du serveur de gestion centralisée, sélectionnez le pool frontal dans la liste déroulante sous **Serveur frontal sur lequel installer le serveur de gestion centralisée**. Un serveur frontal peut être un pool frontal Enterprise Edition ou un serveur frontal Standard Edition.

> [!IMPORTANT]
> Après avoir défini, publié et déployé le magasin central de gestion pour l’infrastructure, vous ne pouvez pas modifier son emplacement sans redéfinir l’emplacement du magasin central de gestion sur un autre serveur frontal par le biais d’un processus externe.

Pour plus d’informations sur le déplacement du magasin central de gestion, reportez-vous à la rubrique [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps) dans la référence de l’applet de commande Windows PowerShell.


Pour plus d’informations sur la définition et la configuration de ces paramètres, reportez-vous à la rubrique [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx).


