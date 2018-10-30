---
title: Téléphones de partie commune dans Lync Server 2013
TOCTitle: Téléphones de partie commune dans Lync Server 2013
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994076(v=OCS.15)
ms:contentKeyID: 53095536
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Téléphones de partie commune dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Les téléphones de partie commune sont des téléphones IP qui ne sont pas associés à un utilisateur individuel. Ils ne sont pas confinés au bureau d’une seule et unique personne mais généralement installés dans des halls d’accueil, des cafétérias, des espaces réservés aux employés, des salles de réunion et d’autres lieux où plusieurs personnes peuvent se rassembler et se retrouver. Contrairement aux autres téléphones dans Lync Server, qui sont généralement soumis à des stratégies de voix et des plans de numérotation attribués à des utilisateurs individuels, aucun utilisateur individuel n’est affecté aux téléphones de partie commune. Cela signifie qu’ils doivent être gérés différemment des autres téléphones.

Pour gérer des téléphones de partie commune, vous devez créer des objets de contacts services de domaine Active Directory pour tous vos téléphones de partie commune auxquels, comme des comptes d’utilisateur, peuvent être assignés des stratégies et des plans vocaux. Cette approche vous permet de conserver le contrôle de vos téléphones de partie commune même s’ils ne sont pas associés à un utilisateur individuel.

Consultez les rubriques de cette section pour découvrir comment créer, modifier ou supprimer des objets de contacts pour les téléphones de partie commune et comment configurer et afficher les informations de configuration sur les téléphones de partie commun de votre déploiement.

> [!NOTE]  
> Il existe trois options de téléphones de partie commune : le téléphone de partie commune Aastra 6721ip, le téléphone IP HP 4110 et le téléphone de partie commune Polycom CX500 IP. Le téléphone de conférence IP Polycom CX3000 est une autre variété de téléphone de partie commune. Toutefois, il est destiné à un usage dans les salles de conférence. Pour plus d’informations sur les téléphones de partie commune, voir la section Téléphones de partie commune dans <a href="http://technet.microsoft.com/fr-fr/library/gg398958(v=ocs.14).aspx">Sélection de nouveaux périphériques</a>.

## Dans cette section

  - [Afficher des informations sur les téléphones de partie commune](lync-server-2013-view-common-area-phone-information.md)

  - [Créer ou modifier un objet contact téléphonique de partie commune](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [Activer ou désactiver le partage de téléphone](lync-server-2013-enable-or-disable-hot-desking.md)

  - [Supprimer un objet contact téléphonique de partie commune](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [Assigner des stratégies à un téléphone de partie commune](lync-server-2013-assign-policies-to-a-common-area-phone.md)

