---
title: 'Lync Server 2013 : Routage des appels E9-1-1 avec une jonction SIP'
TOCTitle: Routage des appels E9-1-1 avec une jonction SIP
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204701(v=OCS.15)
ms:contentKeyID: 49296352
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Routage des appels E9-1-1 avec une jonction SIP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-29_

Se connecter à un fournisseur de services E9-1-1 éligible à l’aide d’une jonction SIP vous permet de déployer E9-1-1. Pour plus d’informations sur la connexion à un fournisseur de services E9-1-1 basé sur une ligne du réseau téléphonique commuté (RTC) à l’aide d’une passerelle ELIN, reportez-vous à [Routage des appels E9-1-1 via une passerelle ELIN dans Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).

Le diagramme suivant illustre la manière dont un appel d’urgence est routé de Lync Server vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP) lorsque vous utilisez une jonction SIP et un fournisseur de services E9-1-1 éligible.

**Routage des appels E9-1-1 via une jonction SIP**

![Routage d’appel d’urgence de Lync Server vers PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Routage d’appel d’urgence de Lync Server vers PSAP")

Lorsque vous effectuez un appel d’urgence à partir d’un client Lync Server compatible :

1.  Une requête SIP INVITE contenant l’emplacement, le numéro de rappel de l’appelant, l’URL de notification (facultatif) et le numéro de rappel de la conférence est routée vers Lync Server.

2.  Lync Server fait concorder le numéro d’urgence et route l’appel (en fonction de la valeur **Utilisation RTC** définie dans la stratégie d’emplacement appropriée) vers un serveur de médiation et, de là, par l’intermédiaire d’une jonction SIP vers un fournisseur de services E9-1-1.

3.  Le fournisseur de services E9-1-1 route l’appel d’urgence vers le centre téléphonique de sécurité publique (PSAP) adéquat en fonction de l’emplacement fourni avec l’appel. Lorsque le client inclut un emplacement de situation d’urgence (ERL) validé dans l’appel d’urgence, le fournisseur route automatiquement l’appel vers le PSAP approprié. Si l’emplacement a été entré manuellement par l’utilisateur, le centre de réponse aux appels d’urgence vérifie d’abord verbalement la précision de l’emplacement auprès de l’appelant avant de router l’appel d’urgence vers le PSAP.

4.  Si vous avez configuré la stratégie d’emplacement pour les notifications, un ou plusieurs responsables de la sécurité reçoivent une notification d’urgence Lync spéciale sous forme de message instantané. Ce message s’affiche toujours sur leur écran et contient le nom, le numéro de téléphone, l’heure et l’emplacement de l’appelant, ce qui permet au personnel chargé de la sécurité de répondre rapidement à l’appel d’urgence par un message instantané ou vocal.

5.  Si vous avez configuré la stratégie d’emplacement pour les conférences et qu’elle est prise en charge par le fournisseur de services E9-1-1, un service de sécurité interne est intégré à l’appel avec des données audio unidirectionnelles ou bidirectionnelles.

6.  Si l’appel se termine prématurément, le PSAP utilise le numéro de rappel pour contacter directement l’appelant.

