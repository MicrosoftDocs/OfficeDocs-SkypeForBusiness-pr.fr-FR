---
title: "Lync Server 2013 : Vérif. de la connectivité entre les serveurs int. et Edge"
TOCTitle: Vérification de la connectivité entre les serveurs internes et les serveurs Edge
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398292(v=OCS.15)
ms:contentKeyID: 49296503
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification de la connectivité entre les serveurs internes et les serveurs Edge dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

Lync Server 2013 comportait un Assistant de validation qui permettait de valider la connectivité entre les serveurs Edge et les serveurs internes. Dans Lync Server 2013, la validation de la connectivité s’effectue automatiquement lorsque vous installez des serveurs Edge.

Vous pouvez valider la réplication des informations de configuration à la périphérie en exécutant l’applet de commande Windows PowerShell**Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne où se trouve le magasin central de gestion (ou tout autre ordinateur lié au domaine sur lequel les composants principaux de Lync Server 2013 (OcsCore.msi) sont installés). Les résultats initiaux peuvent indiquer le statut de réplication « False » au lieu de « True ». Si tel est le cas, exécutez l’applet de commande **Invoke-CsManagementStoreReplication** pour donner à la réplication le temps nécessaire de se terminer avant de réexécuter **Get-CsManagementStoreReplicationStatus**.

Vous pouvez vérifier la connectivité des utilisateurs externes séparément, notamment à l’aide de l’Analyseur de connectivité à distance d’Office Communications Server. Pour plus d’informations, reportez-vous à [Vérification de la connectivité pour les utilisateurs externes dans Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).

