---
title: "Lync Server 2013 : Contr. d’appel distant et normal. des numéros de téléphone"
TOCTitle: Contrôle d’appel distant et normalisation des numéros de téléphone
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558630(v=OCS.15)
ms:contentKeyID: 49296684
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Contrôle d’appel distant et normalisation des numéros de téléphone dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-22_

Les clients Lync téléchargent les règles de normalisation des numéros de téléphone dans le cadre du téléchargement du fichier du Service de carnet d’adresses. Dans les scénarios de contrôle d’appel distant, ces règles s’appliquent aux appels entrants et sortants de contrôle d’appel distant. Pour les appels entrants vers un utilisateur pour lequel le contrôle d’appel distant est activé, le numéro de téléphone de l’appelant est d’abord normalisé au format E.164 par la passerelle SIP/CSTA ou par un système PBX. Lorsque Lync Server 2013 reçoit l’appel provenant de la passerelle, il effectue une recherche de numéro inversée et compare le numéro de l’appelant avec le numéro normalisé dans la liste Contacts Microsoft Office Outlook ou dans la liste d’adresses globale (LAG) stockée dans le Service de carnet d’adresses du destinataire de l’appel. Si une correspondance est trouvée, l’appelant est identifié par son nom dans la notification d’appel entrant.

Pour les appels sortants de contrôle d’appel distant, Lync applique les règles de normalisation des numéros de téléphone du Service de carnet d’adresses au numéro composé avant d’acheminer l’appel vers la passerelle SIP/CSTA.

Pour plus d’informations sur la création de règles de normalisation des numéros de téléphone pour le contrôle d’appel distant, reportez-vous à [Plans de numérotation et règles de normalisation dans Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) dans la documentation de planification.

## Migration des règles de normalisation des numéros de téléphone

Si vous migrez des utilisateurs pour lesquels le contrôle d’appel distant était activé, reportez-vous aux rubriques suivantes dans la documentation de migration :

  - Pour Lync Server 2010, reportez-vous à [Migration du carnet d’adresses](migrate-address-book.md) dans la documentation de migration.

  - Pour Communications Server 2007 R2, reportez-vous à [Migration du carnet d’adresses](migrate-address-book_1.md) dans la documentation de migration.

