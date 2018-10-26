---
title: 'Lync Server 2013 : Routage des appels E9-1-1 via une passerelle ELIN'
TOCTitle: Routage des appels E9-1-1 via une passerelle ELIN
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204919(v=OCS.15)
ms:contentKeyID: 49297323
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Routage des appels E9-1-1 via une passerelle ELIN dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Certains partenaires du programme Unified Communications Open Interoperability fournissent des passerelles compatibles avec les numéros ELIN (Emergency Location Identification Number), ce qui peut servir de solution de remplacement pour une connexion de jonction SIP à un fournisseur de services E9-1-1 qualifié. Les passerelles ELIN prennent en charge la connectivité RNIS (réseau numérique à intégration de services) ou CAMA (Centralized Automatic Message Accounting) aux services E9-1-1 basés sur un réseau téléphonique commuté. Pour plus d’informations sur les partenaires fournissant des passerelles ELIN et obtenir des liens vers la documentation correspondante, reportez-vous à [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425).

Tout comme les connexions de jonctions SIP aux fournisseurs de services E9-1-1, les passerelles ELIN permettent également d’acheminer un appel d’urgence vers le centre téléphonique de sécurité publique (PSAP, Public Safety Answering Point) le plus approprié pour l’appelant. Cependant, ces passerelles utilisent un numéro ELIN comme identificateur d’emplacement. Vous définissez des numéros ELIN pour chaque emplacement de réponse d’urgence (ERL, Emergency Response Location) dans votre organisation (pour plus d’informations, reportez-vous à [Gestion des emplacements pour les passerelles ELIN dans Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).

Quand vous vous servez d’une passerelle ELIN pour les appels d’urgence, vous utilisez la même infrastructure E9-1-1 Lync Server que celle que vous utilisez pour une connexion de jonction SIP. En d’autres termes, la base de données du service d’informations sur l’emplacement fournit l’emplacement au client Lync Server. En outre, la stratégie de localisation active la fonctionnalité et définit le routage. Cependant, avec une passerelle ELIN, vous devez ajouter les numéros ELIN à la base de données du service d’informations sur l’emplacement et indiquer à votre opérateur de réseau téléphonique commuté de les télécharger vers la base de données d’identification automatique de l’emplacement (ALI, Automatic Location Identification).

Quand un client Lync obtient son emplacement à partir du service d’informations sur l’emplacement, cet emplacement inclut le numéro ELIN. Pendant un appel d’urgence, le numéro ELIN est inclus dans les informations d’emplacement envoyées à la passerelle ELIN. La passerelle ELIN identifie l’appel comme un appel d’urgence et remplace le numéro de l’appelant par le numéro ELIN. La passerelle ELIN achemine ensuite l’appel vers le réseau téléphonique commuté en utilisant le numéro ELIN en tant que numéro de l’appelant. Le fournisseur E9-1-1 du réseau téléphonique commuté recherche le numéro ELIN dans la base de données ALI, qui accompagne la base de données MSAG (Master Street Address Guide). Le réseau téléphonique commuté envoie ensuite l’appel au centre PSAP le plus approprié en fonction de la recherche dans la base de données ALI. Le centre PSAP envoie ensuite les premiers intervenants à l’emplacement de l’appelant en fonction de la recherche dans la base de données ALI. Le numéro de l’appelant est mis en cache sur la passerelle ELIN pendant une durée prédéfinie pour les rappels. Lors d’un rappel, le centre PSAP joint la passerelle ELIN, qui remplace le numéro ELIN par le numéro direct de l’appelant.

Les passerelles ELIN prennent en charge les appels d’urgence effectués au sein du réseau de votre organisation. Elles ne prennent pas en charge les appels d’urgence effectués hors de votre réseau.

> [!NOTE]  
> Pour plus d’informations sur l’utilisation d’une connexion de jonction SIP pour les appels d’urgence, reportez-vous à <a href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routage des appels E9-1-1 avec une jonction SIP dans Lync Server 2013</a>.

Le diagramme suivant montre comment un appel d’urgence est acheminé de Lync Server vers le centre PSAP quand vous utilisez une passerelle ELIN.

**Acheminement d’appels E9-1-1 avec une passerelle ELIN**

![Routage des appels ELIN](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "Routage des appels ELIN")

1.  Une requête SIP INVITE contenant l’emplacement, le numéro de rappel de l’appelant, ainsi que l’URL de notification (facultatif) et le numéro de rappel de conférence est acheminée vers Lync Server.

2.  Lync Server établit une correspondance avec le numéro d’urgence. Il achemine ensuite l’appel (en fonction de la valeur **Utilisation RTC** définie dans la stratégie d’emplacement applicable) vers un serveur de médiation, puis vers une passerelle ELIN.

3.  La passerelle ELIN achemine l’appel via une jonction RNIS ou CAMA vers le réseau téléphonique commuté.

4.  Le réseau téléphonique commuté identifie l’appel comme un appel d’urgence et l’achemine vers un routeur sélectif E9-1-1 du réseau. Le routeur sélectif E9-1-1 recherche le numéro de l’appelant dans la base de données ALI afin d’obtenir l’emplacement géographique correspondant. Le routeur sélectif E9-1-1 envoie l’appel au centre PSAP le plus approprié en fonction des informations d’emplacement récupérées à partir de la base de données ALI.

5.  Si vous avez configuré la stratégie d’emplacement pour les notifications, un ou plusieurs responsables de la sécurité reçoivent une notification d’urgence Lync spéciale sous forme de message instantané. Ce message s’affiche toujours sur leur écran et contient le nom, le numéro de téléphone, l’heure et l’emplacement de l’appelant, ce qui permet au personnel chargé de la sécurité de répondre rapidement à l’appel d’urgence par un message instantané ou vocal.

6.  Si l’appel est interrompu prématurément, le centre PSAP utilise le numéro ELIN pour contacter directement l’appelant. La passerelle ELIN remplace le numéro ELIN par le numéro direct de l’appelant.

