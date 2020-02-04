---
title: Ajouter un serveur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
ROBOTS: NOINDEX, NOFOLLOW
description: Pour incorporer un serveur Edge ou un pool de serveurs Edge dans la conception de votre topologie, vous devez spécifier le nom de domaine complet du serveur sur lequel vous voulez déployer le serveur Edge ou le pool de serveurs Edge. Avant de publier une topologie incluant le serveur de périphérie ou le pool de serveurs de périphérie et en installant Skype entreprise Server, vous devez avoir rempli toutes les conditions préalables pour le déploiement de l’accès des utilisateurs externes. Pour plus d’informations sur ces conditions préalables, reportez-vous à la rubrique Preparing for Installation of Servers in the Perimeter Network de la documentation de déploiement.
ms.openlocfilehash: 4d48096d29f3437efa370405639b394c16a31aaa
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702969"
---
# <a name="add-edge-server"></a>Ajouter un serveur Edge

Pour incorporer un serveur Edge ou un pool de serveurs Edge dans la conception de votre topologie, vous devez spécifier le nom de domaine complet du serveur sur lequel vous voulez déployer le serveur Edge ou le pool de serveurs Edge. Avant de publier une topologie incluant le serveur de périphérie ou le pool de serveurs de périphérie et en installant Skype entreprise Server, vous devez avoir rempli toutes les conditions préalables pour le déploiement de l’accès des utilisateurs externes. Pour plus d’informations sur ces conditions préalables, reportez-vous à la rubrique [Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) de la documentation de déploiement.

> [!IMPORTANT]
> Le nom de domaine complet spécifié doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, et non un nom de domaine complet. Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. Vous devez configurer un suffixe DNS sur le nom de l’ordinateur à déployer comme serveur Edge ou pool de serveurs Edge non joint à un domaine.

> [!TIP]
> Si vous pensez mettre en œuvre un pool de serveurs Edge par la suite, sélectionnez **Pool de plusieurs ordinateurs**. Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec équilibrage de la charge, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique. Lorsque vous êtes prêt à ajouter plus d’ordinateurs au pool par la suite, vous devez de nouveau définir le générateur de topologie pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du pool de serveurs de frontière par le biais de l’Assistant Déploiement de Skype entreprise Server. Vous devez également ajouter le nouveau membre du pool aux programmes d’équilibrage de la charge pour le pool, l’équilibrage de la charge DNS ou les programmes d’équilibrage de la charge matérielle. L’interface Edge interne et l’interface Edge externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge. Veillez à ajouter le serveur du nouveau membre au programme d’équilibrage de la charge approprié.

Vous pouvez ajouter la prise en charge de l’accès des utilisateurs externes lors du déploiement initial de la topologie ou le faire par la suite. Pour plus d’informations sur l’ajout de serveurs Edge ou de pool de serveurs Edge à une topologie existante, reportez-vous à la rubrique [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) de la documentation de déploiement des serveurs Edge.


