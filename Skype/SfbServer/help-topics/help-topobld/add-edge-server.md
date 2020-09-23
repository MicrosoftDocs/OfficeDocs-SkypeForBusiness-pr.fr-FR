---
title: Ajouter un serveur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: Pour incorporer un serveur Edge ou un pool de serveurs Edge dans votre conception de topologie, vous devez spécifier le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez déployer le serveur Edge ou le pool de serveurs Edge. Avant de publier une topologie qui inclut le serveur Edge ou le pool de serveurs Edge et d’installer Skype entreprise Server, vous devez avoir complété tous les éléments prérequis pour le déploiement de l’accès des utilisateurs externes. Pour plus d'informations sur ces conditions requises, voir Préparation de l’installation des serveurs dans le réseau de périmètre dans la documentation du déploiement.
ms.openlocfilehash: 379c181336ecc855feb1344e3328a8ffcd38f447
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216745"
---
# <a name="add-edge-server"></a>Ajouter un serveur Edge

Pour incorporer un serveur Edge ou un pool de serveurs Edge dans votre conception de topologie, vous devez spécifier le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez déployer le serveur Edge ou le pool de serveurs Edge. Avant de publier une topologie qui inclut le serveur Edge ou le pool de serveurs Edge et d’installer Skype entreprise Server, vous devez avoir complété tous les éléments prérequis pour le déploiement de l’accès des utilisateurs externes. Pour plus d'informations sur ces conditions requises, voir [Préparation de l’installation des serveurs dans le réseau de périmètre](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) dans la documentation du déploiement.

> [!IMPORTANT]
> Le nom que vous spécifiez doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, non un nom de domaine complet. Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts. Vous devez configurer un suffixe DNS (Domain Name System) sur le nom de l'ordinateur à déployer en tant que serveur Edge ou pool de serveurs Edge non joint à un domaine.

> [!TIP]
> Si vous pensez implémenter un pool de serveurs Edge ultérieurement, sélectionnez **Pool de plusieurs ordinateurs**. Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec charge équilibrée, vous pouvez créer un pool d’ordinateur unique et un pool FQDN pour l’ordinateur unique. Lorsque vous êtes prêt à ajouter d’autres ordinateurs au pool ultérieurement, vous devez à nouveau le générateur de topologies pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le membre du nouveau pool de serveurs Edge via l’Assistant Déploiement de Skype entreprise Server. Vous devez également ajouter le nouveau membre du pool aux programmes d’équilibrage de la charge pour le pool, l’équilibrage de la charge DNS ou les programmes d’équilibrage de la charge matérielle. L’interface Edge interne et l’interface Edge externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge. Veillez à ajouter le serveur du nouveau membre à l’équilibrage de la charge approprié.

Vous pouvez ajouter la prise en charge de l’accès des utilisateurs externes lorsque vous déployez votre topologie initiale ou après avoir déployé votre topologie initiale. Pour plus d’informations sur l’ajout de serveurs Edge ou de pool de serveurs Edge à une topologie existante, reportez-vous à la rubrique [define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) dans la documentation de déploiement du serveur Edge.


