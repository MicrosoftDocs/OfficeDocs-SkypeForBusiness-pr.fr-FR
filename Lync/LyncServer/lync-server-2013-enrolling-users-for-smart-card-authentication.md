---
title: 'Lync Server 2013 : inscriptions des utilisateurs pour l’authentification par carte à puce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a157d5492378771cf40a6438bbf8672efd01412
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>Inscrire des utilisateurs pour l’authentification par carte à puce dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-03_

Il existe généralement deux méthodes pour inscrire des utilisateurs pour l’authentification par carte à puce. La méthode la plus simple consiste à faire en sorte que les utilisateurs s’inscrivent directement pour l’authentification par carte à puce à l’aide de l’inscription Web, tandis que la méthode plus complexe implique l’utilisation d’un agent d’inscription. Cette rubrique se concentre sur l’auto-évaluation des certificats de carte à puce.

Pour plus d’informations sur l’inscription pour le compte des utilisateurs en tant qu’agent d’inscription, voir inscrire des certificats pour le compte d’autres [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367)utilisateurs chez.

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>Pour inscrire les utilisateurs pour l’authentification par carte à puce

1.  Connectez-vous à la station de travail Windows 8 à l’aide des informations d’identification d’un utilisateur à extension Lync.

2.  Lancez Internet Explorer.

3.  Accédez à la page d' **inscriptions Web** de l’autorité de certification ( https://MyCA.contoso.com/certsrv)par exemple,.
    
    <div>
    

    > [!NOTE]  
    > Si vous utilisez Internet Explorer 10, vous devrez peut-être afficher ce site Web en mode de compatibilité.

    
    </div>

4.  Sur la page d' **Accueil** , sélectionnez **demander un certificat**.

5.  Ensuite, sélectionnez **demande avancée**.

6.  Sélectionnez **créer et envoyer une demande à cette autorité de certification**.

7.  Sélectionnez **utilisateur de carte à puce** dans la section **modèle de certificat** et complétez la demande de certificat avancée avec les valeurs suivantes :
    
      - Les **options de clé** confirment les paramètres suivants :
        
          - Sélectionnez la case d’option **créer un nouveau jeu de clés**
        
          - Pour **CSP**, sélectionnez **Microsoft Base Smart Card crypto Provider**
        
          - Pour **l’utilisation**de la clé, sélectionnez **Exchange** (il s’agit de la seule option disponible).
        
          - Pour **taille**de la clé, entrez **2048**
        
          - Vérifier que le **nom du conteneur de clés automatique** est sélectionné
        
          - Laissez les autres cases à cocher désactivées.
    
      - Sous **options supplémentaires** , confirmez les valeurs suivantes :
        
          - Pour **format de demande** , sélectionnez **CMC**.
        
          - Pour **algorithme de hachage** , sélectionnez **SHA1**.
        
          - Pour **nom convivial** , entrez **certificat Smardcard**.

8.  Si vous utilisez un lecteur SmartCard physique, insérez la carte à puce dans l’appareil.

9.  Cliquez sur **Envoyer** pour envoyer la demande de certificat.

10. Lorsque vous y êtes invité, entrez le code confidentiel utilisé pour créer la carte à puce virtuelle.
    
    <div>
    

    > [!NOTE]  
    > La valeur de code confidentiel de la carte à puce virtuelle par défaut est « 12345678 ».

    
    </div>

11. Une fois le certificat émis, cliquez sur **installer ce certificat** pour terminer le processus d’enregistrement.
    
    <div>
    

    > [!NOTE]  
    > Si votre demande de certificat échoue avec l’erreur « ce navigateur Web ne prend pas en charge la génération de demandes de certificats », il existe trois façons de résoudre le problème : 
    > <OL>
    > <LI>
    > <P>Activer l’affichage de compatibilité dans Internet Explorer</P>
    > <LI>
    > <P>Activer l’option Activer les paramètres intranet dans Internet Explorer</P>
    > <LI>
    > <P>Activez le paramètre rétablir toutes les zones au niveau par défaut sous l’onglet sécurité dans le menu options d’Internet Explorer.</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

