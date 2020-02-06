---
title: Définir le nom de domaine complet de la conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Pour ce faire, vous devez créer un serveur de chat permanent ou un pool de serveurs de chat permanent à l’aide de l’Assistant définir un pool de discussions permanent. Sélectionnez un pool comportant plusieurs ordinateurs ou un pool comportant un seul ordinateur. Lorsque vous sélectionnez un pool comportant un seul ordinateur et qu’ensuite vous avez besoin d’un pool comportant plusieurs ordinateurs, vous devez supprimer le pool comportant un seul ordinateur afin de définir un pool comportant plusieurs ordinateurs.
ms.openlocfilehash: 12b5a648de211086d33624afad56ce069493b135
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820196"
---
# <a name="define-persistent-chat-fqdn"></a>Définir le nom de domaine complet de la conversation permanente
 
Pour ce faire, vous devez créer un serveur de chat permanent ou un pool de serveurs de chat permanent à l’aide de l’Assistant **définir un pool de discussions permanent** . Sélectionnez un **pool comportant plusieurs ordinateurs** ou un **pool comportant un seul ordinateur**. Lorsque vous sélectionnez un pool comportant un seul ordinateur et qu’ensuite vous avez besoin d’un pool comportant plusieurs ordinateurs, vous devez supprimer le pool comportant un seul ordinateur afin de définir un pool comportant plusieurs ordinateurs.
  
Vous devez également définir un **nom de domaine complet de pool** pour le serveur de chat permanent ou le pool de serveurs de chat permanent. Le nom de domaine complet (FQDN) du pool d’un seul pool d’ordinateurs doit être identique à celui de l’ordinateur qui compose le pool de serveur unique. Dans le cas d’un pool d’ordinateurs multiples, le nom de domaine complet doit correspondre au nom que vous avez choisi pour représenter ce pool d’ordinateurs et est défini dans DNS par l’enregistrement de l’hôte A (et du protocole AAAA en cas d’utilisation D’ipv6).
  
## <a name="see-also"></a>Voir aussi

[Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Ajouter un serveur de chat permanent à votre topologie 2015 Skype entreprise Server](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
