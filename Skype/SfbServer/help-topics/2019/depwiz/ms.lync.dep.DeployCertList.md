---
title: Liste de certificats
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
ROBOTS: NOINDEX, NOFOLLOW
description: Pour affecter un certificat, sélectionnez un certificat dans le magasin de certificats local. Cliquez sur Suivant pour continuer.
ms.openlocfilehash: 0165afc7a90983855dab8f5a0a2d1c7e44385318
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808914"
---
# <a name="certificate-list"></a>Liste de certificats
 
Pour affecter un certificat, sélectionnez un certificat dans le magasin de certificats local. Cliquez sur **Suivant** pour continuer.
  
Le ou les certificats pouvant être sélectionnés dans le volet **Sélectionner un certificat dans le magasin de certificats local** sont des certificats valides qui peuvent être assignés à l’utilisation du certificat dont vous avez besoin. Vous pouvez confirmer que le certificat que vous sélectionnez est le bon certificat en cliquant sur le bouton **Afficher les détails du certificat**. Sous l’onglet **Détails**, vous pouvez voir le nom du sujet et les autres noms du sujet désignés comme configurés sur le certificat.
  
> [!IMPORTANT]
> Il se peut qu’aucun certificat ne figure dans le volet de sélection. Dans ce cas, la cause est généralement qu’aucun certificat racine approuvé ou certificat d’une autorité de certification intermédiaire n’est installé sur le serveur prévu pour vérifier le certificat et maintenir par conséquent la chaîne d’approbation créée par le certificat avec l’autorité de certification. Pour résoudre ce problème, demandez et importez une chaîne de certificats, qui inclut généralement le certificat de l’autorité de certification racine, ainsi que tous les certificats des autorités de certification intermédiaires et des autorités de certification de délivrance. 
  

