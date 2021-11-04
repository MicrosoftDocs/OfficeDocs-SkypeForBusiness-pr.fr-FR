---
title: Ajouter un magasin SQL
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
ROBOTS: NOINDEX, NOFOLLOW
description: Pour définir une nouvelle SQL Store, ce qui signifie que vous spécifiez une base de données SQL Server et une instance de SQL Server (une instance par défaut ou une instance nommée), vous devez spécifier ce qui suit.
ms.openlocfilehash: fee7fcd3a7d18f9bf6f3c8fe91c3c971c9cdcba0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769332"
---
# <a name="add-sql-store"></a>Ajouter un magasin SQL

Pour définir une nouvelle SQL Store, ce qui signifie que vous spécifiez une base de données SQL Server et une instance de SQL Server (une instance par défaut ou une instance nommée), vous devez spécifier ce qui suit.

Spécifiez le nom de domaine complet (FQDN) de la SQL Server qui hébergera l’instance de base de données que vous définissez.

Spécifiez l’instance de SQL Server qui hébergera les données. Vous pouvez spécifier l’instance par défaut ou une instance nommée.

Vous devez comprendre parfaitement la colocalisation des bases de données dans des instances spécifiques. Pour plus d’informations sur la colocalisation des serveurs et la colocalisation des instances de bases de données, voir [Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment) et [Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment).