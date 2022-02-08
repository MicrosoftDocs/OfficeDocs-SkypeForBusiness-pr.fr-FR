---
title: Ajouter un magasin SQL
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
description: Pour définir une nouvelle SQL Store, ce qui signifie que vous spécifiez une base de données SQL Server et une instance de SQL Server (une instance par défaut ou une instance nommée), vous devez spécifier ce qui suit.
ms.openlocfilehash: e8228063ee3569e1e72683f63af663e13541de03
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384502"
---
# <a name="add-sql-store"></a>Ajouter un magasin SQL

Pour définir une nouvelle SQL Store, ce qui signifie que vous spécifiez une base de données SQL Server et une instance de SQL Server (une instance par défaut ou une instance nommée), vous devez spécifier ce qui suit.

Spécifiez le nom de domaine complet (FQDN) du SQL Server qui hébergera l’instance de base de données que vous définissez.

Spécifiez l’instance de SQL Server qui hébergera les données. Vous pouvez spécifier l’instance par défaut ou une instance nommée.

Vous devez comprendre parfaitement la colocalisation des bases de données dans des instances spécifiques. Pour plus d’informations sur la colocalisation des serveurs et la colocalisation des instances de bases de données, voir [Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment) et [Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment).