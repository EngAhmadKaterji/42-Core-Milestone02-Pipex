# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: akaterji <akaterji@student.42.fr>          +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2024/07/07 14:35:51 by akaterji          #+#    #+#              #
#    Updated: 2024/07/07 17:12:40 by akaterji         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

# Compiler
CC      = gcc
AR      = ar rcs
RM      = rm -f
MD      = mkdir -p
CP      = cp -f

# Directories
SRC_DIR = srcs/
OBJ_DIR = obj/
INC_DIR = includes/
LIBFT   = libft.a
LIBFT_DIR = libft/
LIBFT_AR = $(LIBFT_DIR)$(LIBFT)

# Compiler flags
CFLAGS = -Wall -Wextra -Werror -g
INCLUDES = -Iincludes

# Executable name
NAME = pipex

# Source files
SL_SRCS = pipex_utils.c pipex.c

SRCS := $(addprefix $(SRC_DIR), $(SL_SRCS))
OBJS := $(addprefix $(OBJ_DIR), $(SL_SRCS:.c=.o))

all : $(NAME)

# Compile .c files to .o files
$(OBJ_DIR)%.o: $(SRC_DIR)%.c | $(OBJ_DIR)
	$(CC) $(CFLAGS) $(INCLUDES) -c $< -o $@

# Link object files into executable
$(NAME): $(OBJS) $(LIBFT_AR)
	$(CC) $(CFLAGS) $(OBJS) -o $(NAME) $(LIBFT_AR)

$(LIBFT_AR):
	make -C $(LIBFT_DIR) all

$(OBJ_DIR):
	$(MD) $(OBJ_DIR)

clean:
	$(RM) $(OBJS) $(NAME)
	make -C $(LIBFT_DIR) clean

fclean: clean
	rm -f $(NAME)
	make fclean -C $(LIBFT_DIR)

re: fclean all

.PHONY: all clean fclean re
	