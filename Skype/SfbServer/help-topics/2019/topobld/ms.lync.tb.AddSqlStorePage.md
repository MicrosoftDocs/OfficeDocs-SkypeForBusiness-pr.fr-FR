---
title: Ajouter un magasin SQL
ms.reviewer: ''
ms.author: v-cichur
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
description: Pour définir une nouvelle SQL Store, ce qui signifie que vous spécifiez une base de données SQL Server et une instance de SQL Server (instance par défaut ou instance nommée), vous devez spécifier ce qui suit.
ms.openlocfilehash: a20784ca216d8a1776605089a18e79a6d6f0f3c6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597108"
---
# <a name="add-sql-store"></a>Ajouter un magasin SQL

Pour définir une nouvelle SQL Store, ce qui signifie que vous spécifiez une base de données SQL Server et une instance de SQL Server (instance par défaut ou instance nommée), vous devez spécifier ce qui suit.

Spécifiez le nom de domaine complet (FQDN) de la SQL Server qui hébergera l’instance de base de données que vous définissez.

Spécifiez l’instance de SQL Server qui hébergera les données. Vous pouvez spécifier l’instance par défaut ou une instance nommée.

Vous devez comprendre parfaitement la colocalisation des bases de données dans des instances spécifiques. Pour plus d’informations sur la colocalisation des serveurs et la colocalisation des instances de bases de données, voir [Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment) et [Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment).