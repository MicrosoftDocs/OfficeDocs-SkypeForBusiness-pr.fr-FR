---
title: Ajouter un magasin SQL
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
description: Pour définir une nouvelle SQL Store, ce qui signifie que vous spécifiez une base de données SQL Server et une instance de SQL Server (une instance par défaut ou une instance nommée), vous devez spécifier ce qui suit.
ms.openlocfilehash: 28018a7320bc42761a668aaff385302016781592
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095598"
---
# <a name="add-sql-store"></a>Ajouter un magasin SQL

Pour définir une nouvelle SQL Store, ce qui signifie que vous spécifiez une base de données SQL Server et une instance de SQL Server (instance par défaut ou instance nommée), vous devez spécifier ce qui suit.

Spécifiez le nom de domaine complet (FQDN) du SQL Server qui hébergera l’instance de base de données que vous définissez.

Spécifiez l’instance de SQL Server qui hébergera les données. Vous pouvez spécifier l’instance par défaut ou une instance nommée.

Vous devez comprendre parfaitement la colocalisation des bases de données dans des instances spécifiques. Pour plus d’informations sur la colocalisation des serveurs et la colocalisation des instances de bases de données, voir [Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment) et [Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment).