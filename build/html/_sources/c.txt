===================
C Programming Notes
===================

C Basics
========

Basics
------

& gives the address of an object
* dereferencing operation - gets object pointer points to

alloc(n)
    returns pointer to n consecutive character positions

afree(p)
    releases storage
    - must be made in opposite order to the calls made on alloc

malloc

free

NODE STRUCTURE

struct type_node {
    void * data;
    struct type_node * prev;
    struct type_node * next;
};

main()
{
    struct type_node * head;
    return 0;
}

//allocate space for a structure
struct type_node * pNode;
pNode = talloc(); //talloc routine returns pointer
                  //to a free space to hold the node


IO
----

getline adds '\0' at end of array it reads
so "hello\n" is stored as [h][e][l][l][o][\n][\0]

Register declaration
--------------------

Register declaration

    f(register unsigned m, register long n)
    {
        register int i;
    }

Macro Subsitution
-----------------

Macro Substitution

    #define name replacement text
    #define forever for (;;) /* infinite loop */


Socket Programming
==================

Big-endian        bytes are in a normal order
Little-endian     bytes are backwards

Convert numbers to Network Byte Order before they go out the wire

htons()           Host to Network Short
htonl()           host to network long

Convert them to Host Byte Order as they come in off the wire
ntohs()           network to host short
ntohl()           network to host long

struct addrinfo {
    int              ai_flags;     // AI_PASSIVE, AI_CANONNAME, etc.
    int              ai_family;    // AF_INET, AF_INET6, AF_UNSPEC
    int              ai_socktype;  // SOCK_STREAM, SOCK_DGRAM
    int              ai_protocol;  // use 0 for "any"
    size_t           ai_addrlen;   // size of ai_addr in bytes
    struct sockaddr *ai_addr;      // struct sockaddr_in or _in6
    char            *ai_canonname; // full canonical hostname

    struct addrinfo *ai_next;      // linked list, next node
};

struct sockaddr {
    unsigned short    sa_family;    // address family, AF_xxx
    char              sa_data[14];  // 14 bytes of protocol address
}; 

// (IPv4 only--see struct sockaddr_in6 for IPv6)
struct sockaddr_in {
    short int          sin_family;  // Address family, AF_INET
    unsigned short int sin_port;    // Port number
    struct in_addr     sin_addr;    // Internet address
    unsigned char      sin_zero[8]; // Same size as struct sockaddr
};

// (IPv4 only--see struct in6_addr for IPv6)
// Internet address (a structure for historical reasons)
struct in_addr {
    uint32_t s_addr; // that's a 32-bit int (4 bytes)
};


inet_ntop()            network to presentation

// IPv4:
char ip4[INET_ADDRSTRLEN];  // space to hold the IPv4 string
struct sockaddr_in sa;      // pretend this is loaded with something

inet_ntop(AF_INET, &(sa.sin_addr), ip4, INET_ADDRSTRLEN);
printf("The IPv4 address is: %s\n", ip4);


// IPv6:
char ip6[INET6_ADDRSTRLEN]; // space to hold the IPv6 string
struct sockaddr_in6 sa6;    // pretend this is loaded with something
inet_ntop(AF_INET6, &(sa6.sin6_addr), ip6, INET6_ADDRSTRLEN);
printf("The address is: %s\n", ip6);



#include <sys/types.h>
#include <sys/socket.h>
#include <netdb.h>
int getaddrinfo(const char *node,     // e.g. "www.example.com" or IP
                const char *service,  // e.g. "http" or port number
                const struct addrinfo *hints,
                struct addrinfo **res);
                
int status;
struct addrinfo hints;
struct addrinfo *servinfo;  // will point to the results

memset(&hints, 0, sizeof hints); // make sure the struct is empty
hints.ai_family = AF_UNSPEC;     // don't care IPv4 or IPv6
hints.ai_socktype = SOCK_STREAM; // TCP stream sockets
hints.ai_flags = AI_PASSIVE;     // fill in my IP for me

if ((status = getaddrinfo(NULL, "3490", &hints, &servinfo)) != 0) {
    fprintf(stderr, "getaddrinfo error: %s\n", gai_strerror(status));
    exit(1);
}

// servinfo now points to a linked list of 1 or more struct addrinfos
// ... do everything until you don't need servinfo anymore ....
freeaddrinfo(servinfo); // free the linked-list


